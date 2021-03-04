<script>
  import { url, layout } from '@roxi/routify'
  export let slug;
  const post = $layout.children.filter((c) => c.meta["frontmatter"].slug === decodeURI(slug))[0];
  const blog = post.meta.frontmatter;
</script>

<h1> {blog.slug} </h1>

<h4> {blog.title} </h4>