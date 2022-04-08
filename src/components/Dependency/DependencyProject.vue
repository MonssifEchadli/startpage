<template>
  <div class="row">
    <h5 class="dependances col-lg-6 col-sm-4 col-xs-4">Dependencies</h5>

    <button
      v-b-modal.modal-1
      class="button-35 col-lg-6 col-sm-4 col-xs-4"
      role="button"
    >
      Add Dependency
    </button>

    <b-modal id="modal-1" size="lg" scrollable title="Add Dependency">
      <input
        class="form-control"
        type="text"
        placeholder="Search"
        aria-label="Search"
        v-model="search"
      />
      <div>
        <div class="title-design"><span>DEVELOPER TOOLS</span></div>
        <div v-for="(categorie, index) in filteredDependencies" :key="index">
          <div v-if="categorie.type=='DEVELOPER TOOLS'" class="bordure-hover">
            <h5>{{ categorie.name }}</h5>
            <p>
              {{ categorie.description }}
            </p>
          </div>
        </div>
        <div class="title-design"><span>WEB</span></div>
        <div v-for="(categorie, index) in filteredDependencies" :key="index">
          <div v-if="categorie.type=='WEB'" class="bordure-hover">
            <h5>{{ categorie.name }}</h5>
            <p>
              {{ categorie.description }}
            </p>
          </div>
        </div>
      </div>
    </b-modal>
    <hr />

    <span style="font-style: italic">No Dependency Selected</span>
    <!-- HTML !-->
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: "",
      dependanceSpring : [
        {
          id:"1",
          type: "DEVELOPER TOOLS",
          name: "Spring Native [Experimental]",
          searchParam: "SpringNative[Experimental]",
          description:
            "Incubating support for compiling Spring applications to native executables using the GraalVM native-image comiler.",
        },
        {
          id:"2",
          type: "DEVELOPER TOOLS",
          name: "Spring Boot DevTools",
          searchParam: "SpringBootDevTools",
          description:
            "Provides fast application restarts, LiveReload, and configurations for enhanced development experience.",
        },
        {
          id:"3",
          type: "DEVELOPER TOOLS",
          name: "Lombok",
          searchParam: "Lombok",
          description:
            "Java annotation library which helps to reduce boilerplate code.",
        },
        {
          id:"4",
          type: "DEVELOPER TOOLS",
          name: "Spring Configuration Processor",
          searchParam: "SpringConfigurationProcessor",
          description:
            "Java annotation library which helps to reduce boilerplate code.",
        },
        {
          id:"5",
          type: "WEB",
          name: "Spring Web",
          searchParam: "SpringWeb",
          description:
            "Build web, including RESTful, applications using Spring MVC, Uses Apahce Tomcat as the default embedded container.",
        },
        {
          id:"6",
          type: "WEB",
          name: "Spring Reactive Web",
          searchParam: "SpringReactiveWeb",
          description:
            "Build reactive web applications with Spring WebFlux and Netty",
        },
      ]
    };
  },
  methods: {

  },
  computed: {
    filteredDependencies() {
      return this.dependanceSpring.filter((dependance) => {
        return dependance.name.toLowerCase().replaceAll(' ', '').match(this.search.toLowerCase().replaceAll(' ', ''))
      })
    }
  }
};
</script>

<style scoped>
.bordure-hover {
  border-top: 1px solid #ccc;
  padding: 10px 20px;
  padding-bottom: 3px;
  width: 100%;
}
.bordure-hover:hover {
  color: #fff;
  background-color: #6db33f;
  cursor: pointer;
}

.button-35 {
  align-items: flex-start;
  background-color: #fff;
  border-radius: 5px;
  box-shadow: transparent 0 0 0 3px, rgba(18, 18, 18, 0.1) 0 3px 3px;
  box-sizing: border-box;
  color: #121212;
  cursor: pointer;
  display: inline-flex;
  flex: 1 1 auto;
  font-family: Inter, sans-serif;
  font-size: 1.2rem;
  font-weight: 700;
  justify-content: flex-start;
  line-height: 1;
  margin: 0;
  outline: none;
  padding: 2% 2% 2% 4%;
  margin-bottom: 2%;
  text-align: start;
  text-decoration: none;
  transition: box-shadow 0.2s, -webkit-box-shadow 0.2s;
  white-space: nowrap;
  border: 0;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-35:hover {
  box-shadow: #121212 0 0 0 3px, transparent 0 0 0 0;
}

.dependances {
  margin-top: 2%;
}

.title-design {
  margin: 3% 0 2% 3%;
}

.title-design span {
  background-color: #6db33f;
  color: white;
  padding: 4px;
}

hr {
  margin-top: 8px;
}

@media only screen and (max-width: 1000px) {
  .dependances {
    margin-top: 4%;
  }
  .button-35 {
    margin: 2% 10%;
  }
}

@media only screen and (max-width: 600px) {
  .dependances {
    margin-top: 10%;
  }
}
</style>