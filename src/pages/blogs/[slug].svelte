<script>
  import { url, layout} from '@roxi/routify'
  export let slug;  

  import Marker from "marked"
  
  // We need to get the slug manually now since the page doesn't have a /slug anymore
  slug = decodeURI($url().replace("/", ""));
  
  let post = $layout.children.filter((c) => c.meta["frontmatter"].slug === slug)[0];
  if (post == undefined)
  {
    // We should redirect to _fallback page
    console.warn(`Could not find child matching slug of ${slug}`)
  }
  const blog = post.meta.frontmatter;

</script>
<style global>
 .main{
   width: 60%;
   margin: auto;
 }
 .main > * {
   text-align: center;
 }

 .img-container{
    display: flex;
    justify-content: center;
 }
</style>

<h4> {blog.title} </h4>

<h5> Categories</h5>
{#each blog.Categories as cat }
  <p style="text-align:center">{cat}</p>
{/each}


<div class="img-container">
  <img style="margin:auto;" width="350px" src={blog.thumbnail} >
</div>

<div class="main">
 {@html Marker(blog.main)}
</div>


<h4> written by {blog.author} </h4>