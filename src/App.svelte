<script>
  import { Router } from "@roxi/routify";
  import { routes } from "../.routify/routes";
  // const config = {
  //   urlTransform: {
  //     apply: url => { 
  //       test = url;
  //       let x = url.split("/")[2];
  //       let response = `http://localhost:5005${url}`;
  //       // for testing 
  //       // issues this will update the url in the browser from blogs/blog to /blog
  //       // the problem is that the remove function below will receive the updated url 
  //       // and not the orginal ie remove function has /blog instead of blogs/blog
  //       // this means the interal path to our file is wrong
  //       if(x && x.includes("blog")) {
  //          response = `http://localhost:5005/${x}`
  //       }
  //       return response;
  //     }, //external URL
  //     remove: url => {
  //       return `blogs/blog`;
  //     }, //internal URL
  //   }
  // }

</script>

<style  global>
  @import "../static/global.css";
</style>

<Router {routes}  />