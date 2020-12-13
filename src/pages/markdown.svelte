<script>
  import { layout } from "@roxi/routify";
  import marked from "marked";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "markdown")
  console.log('@cmsData: ', cmsData);
  
</script>
<style>
  main {
    background: #8fD5Db;
    height: 100%;
    overflow: auto;
  }
</style>

<!-- routify:options index=1 -->
<main>
  <br />
  <h1>{cmsData.title}</h1>
  <section class="content">
    {@html marked(cmsData.text)}
  </section>
</main>
