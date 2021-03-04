<script>
  import { Router } from "@roxi/routify";
  import { routes } from "../.routify/routes";

  let blogPostRoute = routes.filter(route => route.file == '[slug].svelte')[0];
  let fallbackRoute = routes.filter(route => route.file == '_fallback.svelte')[0];

  console.log(blogPostRoute);
  // Override the options to remove /blog from the urls
  blogPostRoute.path = blogPostRoute.path.replace("/blogs", "");        
  blogPostRoute.regex = blogPostRoute.regex.replace("/blogs", "")
  blogPostRoute.shortPath = blogPostRoute.shortPath.replace("/blogs", "")   

  // Move the new blog route after other routes
  routes.push(routes.splice(routes.indexOf(blogPostRoute), 1)[0]);
  // Make sure that the fallback route is last
  routes.push(routes.splice(routes.indexOf(fallbackRoute), 1)[0]);
  
</script>

<style  global>
  @import "../static/global.css";
</style>

<Router {routes} />