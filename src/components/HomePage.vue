<template>
  <div style="overflow-x: hidden; height: 100% !important;">
    <div class="row" style="">
      <div class="col-12">
        <div class="row contentmain">
          <div class="col-12"><header-logo></header-logo></div>
          <hr>
          <div class="col-lg-6 col-sm-12 col-xs-12"><configuration-project></configuration-project></div>
          <div class="col-lg-6 col-sm-12 col-xs-12"><dependency-project></dependency-project></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderLogo from "./Configuration/HeaderLogo.vue";
import DependencyProject from "./Dependency/DependencyProject.vue";
import ConfigurationProject from "./Configuration/ConfigurationProject.vue"

export default {
  components: {
    HeaderLogo,
    ConfigurationProject,
    DependencyProject
  },
};
</script>

<style scoped>
.contentmain{
    padding: 0 4%;
    margin: 0 8%;
    border-left: 1px solid #ccc;
    border-right: 1px solid #ccc;
}
</style>