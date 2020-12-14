<!-- routify:options index=0 -->
<script>
  import { metatags } from '@roxi/routify'
  metatags.title = 'NetlifyCMS & Routify'
  metatags.description = 'Demo integration of NetlifyCMS with Routify'

  import marked from "marked";
  import { layout } from "@roxi/routify";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  
  const cmsData = getCMSData($layout, "homepage")

</script>

<style>
  main {
    background: #7fc5bb;
    background: url("/images/hero_1.jpg");
    height: 100%;
    overflow: auto;
    background-position: right;
    background-size: cover;
  }

  p { 
    text-align: center;
    text-shadow: 0 0 0.5rem #ffe198; 
  }
  
  h1 {
    font-size: 7vw;
    text-shadow: 0 0 1rem #DDD;
  }
  @media (max-width:768px) {
    h1 {
      font-size: 5rem;
      margin-top: 0.1rem;
      margin-bottom: 0.25rem;
      margin: 0;
    }
  }
</style>

<main>
  <br />
  <h1>{cmsData.title}</h1>
  <div class="content">
    {@html marked(cmsData.text)}
  </div>
</main>