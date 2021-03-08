<script >
  import { layout, url , params } from "@roxi/routify";
  let posts = $layout.children
    .filter((c) => c.meta["frontmatter"])

  let pageSize  = 1;
  let results;
  let totalPages = (posts.length / 1);
  $: pageNumber = $params.page | 0;
  $: {
    if(pageNumber == 0){
      pageNumber = 1;
    }
    
    results = posts.slice((pageNumber - 1) * pageSize, pageNumber * pageSize) 
  }

</script>
  <style>
    img {
      max-width: 15rem;
      display: block;
      margin: auto;
      border-radius: 50%;
  
    }
    ul {
      display: flex;
      flex-wrap: wrap;
      padding: 0 2rem;
      /* align-items: flex-start; */
      justify-content: space-around;
    }
    li {
      list-style: none;
      min-width: 25rem;
      max-width: 32rem;
      box-shadow: 0px 15px 25px -4px rgba(30,30,60,0.25);
      border-radius: 1rem;
      padding: 1rem;
      margin: 2rem;
    }

    .card {
        background: white;
    }
  </style>
  
  
  <h1>Bonjour Blogs</h1>
  <ul class="posts">
    {#each results as {meta, path}}
      <li class="card"> 
        <a class="title" href="/{meta.frontmatter.slug}">{meta.frontmatter.title}</a>
      </li>
    {/each}
  </ul>
  <br>


  {#if totalPages != pageNumber}
    <a href={$url(`/fr/blogs?page=${pageNumber + 1}`)}> Next</a>
  {/if}

  {#if pageNumber != 1 }
    <a href={$url(`/fr/blogs?page=${pageNumber - 1}`)}> Previous </a>
  {/if}