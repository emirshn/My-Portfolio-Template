<template>
  <v-app id="home">
    <NavBar />
    <v-container fluid>
      <div class="head">
        <v-row>
          <v-col cols="5">
            <div style="position: relative" class="mt-16">
              <h1 class="text-white">Hello.</h1>
              <h1 class="text-white">I'm Lorem</h1>
              <span class="text-white">Lorem Developer</span> <br />
              <v-btn
                @click="scroll('contact')"
                tile
                dark
                class="text-white mt-8"
                variant="outlined"
                >Contact Me</v-btn
              >
            </div>
          </v-col>
          <v-col cols="2">
            <div
              style="
                position: absolute;
                z-index: 9999;
                bottom: 0;
                margin-left: auto;
                margin-right: auto;
                left: 0;
                right: 0;
                text-align: center;
              "
              class="mt-16"
            >
              <v-icon>fas fa-angle-double-down</v-icon>
            </div>
          </v-col>
          <v-col cols="5">
            <div
              style="position: relative; z-index: 9999; transform: scaleX(-1)"
              class="mt-16"
            >
              <v-img src="image1.png" contain max-height="300"></v-img>
            </div>
          </v-col>
        </v-row>
      </div>

      <v-col cols="12" class="mt-16" id="about">
        <div>
          <v-row>
            <v-col cols="12" sm="6">
              <div class="egg">
                <v-img src="image2.png" max-height="500"></v-img>
              </div>
            </v-col>
            <v-col cols="12" sm="6">
              <h5 class="mt-16">About Me</h5>
              <div style="width: 120px">
                <v-slider v-model="slider2" color="#2494f4"></v-slider>
              </div>
              <h4 class="mt-n4">I am a Lorem Developer</h4>
              <h4>And Lorem</h4>
              <p class="text-grey">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
                enim ad minim veniam, quis nostrud exercitation ullamco laboris
                nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor
                in reprehenderit in voluptate velit esse cillum dolore eu fugiat
                nulla pariatur.
              </p>
              <br />
              <p class="text-grey">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
                enim ad minim veniam, quis nostrud exercitation ullamco laboris
                nisi ut aliquip ex ea commodo consequat.
              </p>
              <v-btn tile dark color="blue" class="mt-4">
                <a
                  style="text-decoration: none; color: white"
                  href="/files/Resume.pdf"
                  download
                  >Download Resume</a
                >
              </v-btn>
            </v-col>
          </v-row>
        </div>
      </v-col>

      <div class="text-center mt-5">
        <h2>What Can I Do</h2>
        <div style="width: 120px; margin: 0 auto">
          <v-slider v-model="slider2" color="blue"></v-slider>
        </div>
      </div>

      <v-col cols="12" class="mt-1" id="projects">
        <div class="first mb-19" id="project">
          <v-row>
            <v-col cols="12">
              <div class="child">
                <v-btn
                  icon="fas fa-laptop-code"
                  color="blue"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">Lorem Development</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Lorem, ipsum dolor sit amet <br />consectetur adipisicing
                  <br />consectetur adipis
                </p>
              </div>
              <div class="child">
                <v-btn
                  icon="fas fa-brands fa-css3"
                  color="blue"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">Web Design</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Lorem, ipsum dolor sit amet <br />consectetur adipisicing
                  <br />consectetur adipis
                </p>
              </div>
              <div class="child">
                <v-btn
                  icon="fas fa-solid fa-code"
                  color="blue"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">Coding</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Lorem, ipsum dolor sit amet <br />consectetur adipisicing
                  <br />consectetur adipis
                </p>
              </div>
              <div class="child">
                <v-btn
                  icon="fas fa-hat-wizard"
                  color="blue"
                  class="text-white"
                ></v-btn>
                <h3 class="ml-3 mt-4">3D Modelling and 2D Art</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Lorem, ipsum dolor sit amet <br />consectetur adipisicing
                  <br />consectetur adipis
                </p>
              </div>
            </v-col>
          </v-row>
          <v-divider></v-divider>
        </div>
      </v-col>

      <v-col cols="12" sm="12" id="">
        <div class="d-flex justify-center mb-6">
          <v-btn @click="filterProjects('all')" color="blue" class="mr-2"
            >All</v-btn
          >
          <v-btn
            @click="filterProjects('frontend')"
            color="blue"
            variant="tonal"
            class="mr-2"
            >Frontend</v-btn
          >
          <v-btn
            @click="filterProjects('webdesign')"
            color="blue"
            variant="tonal"
            class="mr-2"
            >Web design</v-btn
          >
          <v-btn
            @click="filterProjects('modelling')"
            color="blue"
            variant="tonal"
            class="mr-2"
            >3D modelling</v-btn
          >
          <v-btn
            @click="filterProjects('others')"
            color="blue"
            variant="tonal"
            class="mr-2"
            >Others</v-btn
          >
        </div>
      </v-col>

      <v-col cols="12" class="imgHover">
        <v-row class="fill-height" align="center" justify="center">
          <template v-for="(item, i) in this.filteredProjects" :key="i">
            <v-col cols="12" md="4">
              <v-hover v-slot="{ isHovering, props }">
                <v-card
                  :elevation="isHovering ? 12 : 2"
                  :class="{ 'on-hover': isHovering }"
                  v-bind="props"
                >
                  <v-img :src="item.img" height="225px" cover> </v-img>
                  <v-row>
                    <v-col cols="9">
                      <h3 class="mt-3 ml-1">{{ item.title }}</h3>
                    </v-col>
                    <v-col cols="2">
                      <v-btn
                        v-if="item.link"
                        variant="plain"
                        @click="loadLink(item.link)"
                        class="mr-1 mt-2"
                      >
                        <!-- <a class="mt-3 ml-1" :href="item.link" target="_blank"
                          >Link</a
                        > -->
                        Link
                      </v-btn>
                    </v-col>
                  </v-row>
                </v-card>
              </v-hover>
            </v-col>
          </template>
        </v-row>
      </v-col>
      <v-col cols="12" sm="12">
        <div class="d-flex justify-center mb-6">
          <v-btn color="#FBDF7E" class="mt-4" @click="loadLink()"
            >For More</v-btn
          >
        </div>
      </v-col>

      <v-col cols="12" sm="12" class="px-16" id="contact">
        <div>
          <v-row>
            <v-col cols="12" sm="">
              <div style="text-align: center">
                <h1>Contact info.</h1>
                <div>
                  <div class="child">
                    <v-btn
                      icon="fas fa-map-marker-alt"
                      color=""
                      class=""
                      variant="outlined"
                    ></v-btn
                    ><br />
                    <span class="text-caption">Earth / Earth </span><br />
                  </div>
                  <div class="child">
                    <v-btn
                      icon="fas fa-phone-alt"
                      color=""
                      class=""
                      variant="outlined"
                    ></v-btn
                    ><br />
                    <span class="text-caption">555 555 55 55 </span> <br />
                  </div>
                  <div class="child">
                    <v-btn
                      href="mailto:"
                      icon="fas fa-envelope"
                      color=""
                      class=""
                      variant="outlined"
                    ></v-btn
                    ><br />
                    <span class="text-caption">lorem.com </span>
                    <br />
                  </div>
                  <div class="child">
                    <v-btn
                      @click="loadLink()"
                      icon="fas fa-brands fa-linkedin"
                      color=""
                      class=""
                      variant="outlined"
                    ></v-btn
                    ><br />
                    <span class="text-caption">Linkedin </span> <br />
                  </div>
                  <div class="child">
                    <v-btn
                      @click="loadLink()"
                      icon="fas fa-brands fa-github"
                      color=""
                      class=""
                      variant="outlined"
                    ></v-btn
                    ><br />
                    <span class="text-caption">Github </span> <br />
                  </div>
                </div>
              </div>
            </v-col>
          </v-row>
        </div>
      </v-col>
      <FooterBar></FooterBar>
    </v-container>
  </v-app>
</template>

<script>
import NavBar from "../components/NavBar.vue";
import FooterBar from "../components/FooterBar.vue";
export default {
  components: {
    NavBar,
    FooterBar,
  },
  data() {
    return {
      slider2: 50,

      filteredProjects: [],

      projects: [
        {
          img: "i3.jpg",
          title: "Lorem",
          link: "",
          types: ["frontend", "webdesign"],
        },
        {
          img: "i4.jpg",
          title: "Lorem",
          link: "",
          types: ["frontend"],
        },
        {
          img: "i5.jpg",
          title: "Lorem",
          link: "",
          types: ["frontend", "modelling"],
        },
        {
          img: "i6.jpeg",
          title: "Lorem",
          link: "",
          types: ["others", ],
        },
      
      ],
    };
  },
  created() {
    this.filteredProjects = this.projects;
  },
  methods: {
    loadLink(link) {
      window.open(link, "_blank");
    },
    filterProjects(filter) {
      if (filter === "all") {
        this.filteredProjects = this.projects;
      } else {
        const filterByTags = [filter];
        const filterByTagSet = new Set(filterByTags);
        this.filteredProjects = this.projects.filter((o) =>
          o.types.some((tag) => filterByTagSet.has(tag))
        );
        console.log(this.filteredProjects);
      }
    },
    scroll(refName) {
      const element = document.getElementById(refName);
      element.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
.doubleArrow {
  position: absolute;
  z-index: 9999;
  bottom: 0;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  text-align: center;
  margin-top: 16px;
}
.v-container {
  padding: 16px 0;
}
.head {
  position: relative;
  text-align: center;
  padding: 12px;
  margin-bottom: 6px;
  height: 400px;
  width: 100%;
  color: white;
}
.head:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 50%;
  background: #2494f4;
  transform: skew(0deg, 6deg);
}
.head:after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 50%;
  background: #2494f4;
  transform: skew(0deg, -6deg);
}
.egg {
  display: block;
  margin-left: 200px;
  margin-top: 75px;
  width: 300px;
  height: 300px;
  background-color: #4c9de5;
  border-radius: 50% 50% 50% 50% /50% 50% 50% 50%;
}
.first {
  width: 100%;
  height: 280px;
  text-align: center;
  padding: 2rem 2rem;
}
.child {
  display: inline-block;
  padding: 2rem 1rem;
  vertical-align: middle;
  text-align: center;
  margin-right: 8px;
}
.imgHover {
  padding: 0 200px;
}
.pre {
  width: 100%;
  height: 380px;
  text-align: center;
  padding: 0 200px;
  background-color: #f5f5f5;
}
.hire {
  width: 100%;
  height: 200px;
  padding: 0 200px;
  background-color: #e9e9e9;
  margin-top: -24px;
}
</style>
