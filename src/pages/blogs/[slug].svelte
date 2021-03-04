<script>
  import { url, layout, page,goto } from '@roxi/routify'
  export let slug;  
  
  // We need to get the slug manually now since the page doesn't have a /slug anymore
  slug = decodeURI($url().replace("/", ""));
  
  let post = $layout.children.filter((c) => c.meta["frontmatter"].slug === slug)[0];
  post = undefined;
  if (post == undefined)
  {
    // We should redirect to _fallback page
    console.warn(`Could not find child matching slug of ${slug}`)
  }

  const blog = post.meta.frontmatter;
</script>

<h1> {blog.slug} </h1>

<h4> {blog.title} </h4>