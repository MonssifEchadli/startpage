<template>
  <div class="bordure">
      <div class="row">
          <div class="col-lg-6 col-sm-6 col-xs-12" ><project-choice></project-choice></div>
          <div class="col-lg-6 col-sm-6 col-xs-12"><language-choice></language-choice></div>
      </div>
      <div class="row">
          <div style="margin-top: 2%" class="col-12"><spring-boot></spring-boot></div>
      </div>
      <div class="row">
          <div style="margin-top: 2%" class="col-12"><meta-data></meta-data></div>
      </div>
      <br>
      <div class="row">
          <div class="col-lg-6 col-sm-6 col-xs-12" ><packaging-choice></packaging-choice></div>
          <div class="col-lg-6 col-sm-6 col-xs-12"><java-version></java-version></div>
      </div>
  </div>
</template>

<script>
import ProjectChoice from './ProjectChoice.vue'
import LanguageChoice from './LanguageChoice.vue'
import SpringBoot from './SpringBoot.vue'
import MetaData from './MetaData.vue'
import PackagingChoice from './PackagingChoice.vue'
import JavaVersion from './JavaVersion.vue'
export default {
  components : {
      ProjectChoice,
      LanguageChoice,
      SpringBoot,
      MetaData,
      PackagingChoice,
      JavaVersion
  }
}
</script>

<style scoped>

@media only screen and (min-width: 1000px) {
    .bordure{
        border-right: 1px solid #ccc;
        padding-right: 3%;
    }
}

</style>