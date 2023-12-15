<template>
      <div class="accueil pt-20 pb-4">
            <div class="accueil__swipe">
                  <!--La partie du slide-->
                  <swiper
                        :spaceBetween="30"
                        :centeredSlides="true"
                        :autoplay="{
                              delay: 3500,
                              disableOnInteraction: false,
                        }"
                        :pagination="{
                              clickable: true,
                        }"
                        :navigation="true"
                        :modules="modules"
                        class="monSwipe mb-4 container"
                  >
                        <swiper-slide
                              class="monSwipe__capture"
                              v-for="accueil in accueils"
                              :key="accueil.id"
                        >
                              <img :src="accueil.img" alt="" />
                        </swiper-slide>
                  </swiper>

                  <!--La partie du slide pour la version tablette-->
                  <swiper
                        :spaceBetween="30"
                        :centeredSlides="true"
                        :autoplay="{
                              delay: 3500,
                              disableOnInteraction: false,
                        }"
                        :pagination="{
                              clickable: true,
                        }"
                        :navigation="true"
                        :modules="modules"
                        class="monSwipeTablette mb-4 container"
                  >
                        <swiper-slide
                              class="monSwipeTablette__capture"
                              v-for="accueil in accueilsTablette"
                              :key="accueil.id"
                        >
                              <img :src="accueil.img" alt="" />
                        </swiper-slide>
                  </swiper>
            </div>

            <!--La partie de Bienvenue-->
            <div class="accueil__description bg-green-700 bg-opacity-90">
                  <h1 class="font-medium">
                        Welcome to Hauville in the thatched cottage of Gîte du
                        Cormier.
                  </h1>
                  <div>
                        <p>
                              Cécile and Gérard welcome you to the heart of the
                              Norman hinterland. <br />
                              In the loops of the Seine. <br />
                              7 minutes from the A13 and A28 highways. <br />
                              25 minutes from the center of Rouen (76).
                        </p>
                  </div>
            </div>

            <br />

            <!--La partie vidéo -->
            <div class="accueil__video">
                  <video
                        src="../assets/Vidéo/video_presentation_cormier.mp4"
                        type="video/mp4"
                        controls
                        data-aos="fade-right"
                        data-aos-duration="700"
                        data-aos-easing="ease-in-out"
                  ></video>
            </div>

            <br />

            <!---------------Gallerie des 4 photos ---------------------------------------->
            <div class="accueil__gallery mb-6">
                  <div
                        class="accueil__gallery--items"
                        @click="Cliquer"
                        data-aos="fade-right"
                        data-aos-duration="700"
                        data-aos-easing="ease-in-out"
                  >
                        <img
                              src="../../public/pictures/descriptif/jardin/jeux_enfants.jpg"
                              alt="Jeux pour les enfants - gite le cormier"
                        />
                        <div>
                              <h2>
                                    To entertain the children.

                                    <br />

                                    <font-awesome-icon
                                          icon="fa-solid fa-magnifying-glass-plus"
                                          class="plus"
                                    />
                              </h2>
                        </div>

                        <div class="accueil__gallery--text text-left">
                              <div>
                                    To expend energy, <br />
                                    To have fun, <br />
                                    To jump, <br />
                                    To shout, <br />
                                    To play...
                              </div>
                        </div>
                  </div>

                  <div
                        class="accueil__gallery--items"
                        @click="Cliquer"
                        data-aos="fade-right"
                        data-aos-duration="700"
                        data-aos-easing="ease-in-out"
                  >
                        <img
                              src="../../public/pictures/descriptif/jardin/jaccuzzi.jpg"
                              alt="Le jaccuzzi du jardin - gite le cormier"
                        />
                        <div>
                              <h2>
                                    To enjoy the stars

                                    <br />

                                    <font-awesome-icon
                                          icon="fa-solid fa-magnifying-glass-plus"
                                          class="plus"
                                    />
                              </h2>
                        </div>

                        <div class="accueil__gallery--text">
                              <div>
                                    At sunset, <br />
                                    Or after dinner, to contemplate the Milky
                                    Way, <br />
                                    The small bubbles in the 38-degree Jacuzzi
                                    will make you forget everything.
                              </div>
                        </div>
                  </div>

                  <div
                        class="accueil__gallery--items"
                        @click="Cliquer"
                        data-aos="fade-right"
                        data-aos-duration="700"
                        data-aos-easing="ease-in-out"
                  >
                        <img
                              src="../assets/RezDeChaussee/rdc_chaumiere3.jpg"
                              alt="Chaumière du rez de chausse - gite le cormier"
                        />
                        <div>
                              <h2 class="title">
                                    To enjoy winter

                                    <font-awesome-icon
                                          icon="fa-solid fa-magnifying-glass-plus"
                                          class="plus"
                                    />
                              </h2>
                        </div>

                        <div class="accueil__gallery--text text-left">
                              <div>
                                    The open hearth fireplace, <br />
                                    The heart of the 18th-century cottage.
                                    <br />

                                    The fire joins the aperitif, <br />
                                    The shadows and crackling capture the
                                    attention of young and old alike.
                              </div>
                        </div>
                  </div>

                  <div
                        class="accueil__gallery--items"
                        @click="Cliquer"
                        data-aos="fade-right"
                        data-aos-duration="700"
                        data-aos-easing="ease-in-out"
                  >
                        <img
                              src="../assets/Cormier/cormier_ping_pong.jpg"
                              alt="Terrain de Ping Pong - gite le cormier"
                        />

                        <div>
                              <h2>
                                    To have fun as a family

                                    <font-awesome-icon
                                          icon="fa-solid fa-magnifying-glass-plus"
                                          class="plus"
                                    />
                              </h2>
                        </div>

                        <div class="accueil__gallery--text">
                              <div>
                                    For the Grand Slam tournament, <br />
                                    Whoever loses wins... <br />
                                    Wins the right to clear the table.
                              </div>
                        </div>
                  </div>
            </div>

            <div class="accueil__popup">
                  <span @click="fermer">&times;</span>

                  <div
                        class="accueil__popup--main flex justify-around w-4/5 m-auto pt-12"
                  >
                        <div class="w-4/5 transition-all">
                              <img src="" alt="" />
                        </div>

                        <div class="accueil__popup--paragraph"></div>
                  </div>
            </div>
      </div>
</template>

<script>
// Import Swiper Vue.js components
import { computed } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { accueils, accueilsTablette } from "../database/accueil";

// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";
import "swiper/css/navigation";

//import './style.css';

//import "./main.css";
import "../../src/main.css";

// import required modules
import { Autoplay, Pagination, Navigation } from "swiper";
import store from "@/store";

export default {
      components: {
            Swiper,
            SwiperSlide,
      },

      setup() {
            // Cette fonction permet d'agrandir l'image en cliquant sur son div parent

            const Cliquer = () => {
                  const items = document.querySelectorAll(
                        ".accueil__gallery--items"
                  );

                  items.forEach((image) => {
                        image.onclick = (e) => {
                              const source =
                                    e.currentTarget.querySelector("img").src;
                              document.querySelector(
                                    ".accueil__popup"
                              ).style.display = "block";
                              document.querySelector(
                                    ".accueil__popup img"
                              ).src = source;

                              // Pour récupérer le paragraphe de l'image
                              const myText = e.currentTarget.querySelector(
                                    "div.accueil__gallery--text"
                              ).innerHTML;

                              // Pour affecter le paragraphe de l'image dans la classe accueil__popup--paragraph
                              document.querySelector(
                                    "div.accueil__popup--paragraph"
                              ).innerHTML = myText;
                        };
                  });
            };

            // Cette fonction permet de fermer l'image qui sera affiché

            const fermer = () => {
                  document.querySelector(".accueil__popup span").onclick =
                        () => {
                              document.querySelector(
                                    ".accueil__popup"
                              ).style.display = "none";
                        };
            };

            var chooseEnglishVersion = computed(() => {
                  return store.state.englishVersion;
            });

            return {
                  fermer,
                  Cliquer,
                  chooseEnglishVersion,
                  accueils,
                  accueilsTablette,
                  modules: [Autoplay, Pagination, Navigation],
            };
      },
};
</script>

<style lang="scss" scoped>
.accueil {
      @media screen and (max-width: 550px) {
            padding-top: 3em;
      }
      &__swipe {
            .monSwipe {
                  width: 70%;
                  height: 65vh;
                  margin-bottom: 1.5em;

                  @media (max-width: 769px) {
                        display: none;
                  }

                  &__capture {
                        img {
                              width: 100%;
                              margin: auto;
                              max-width: 1380px;
                              min-width: 800px;
                              height: 100%;
                              object-fit: contain;
                        }
                  }
            }

            .monSwipeTablette {
                  display: none;

                  @media (max-width: 769px) {
                        display: block;
                        width: 80%;
                        height: 50vh;
                        margin-top: 2em;
                  }

                  /*@media (max-width: 550px){
                        display: none;
                  }*/

                  @media (max-width: 550px) {
                        display: block;
                        width: 90%;
                        height: 300px;
                        margin-top: 1em;
                  }

                  &__capture {
                        img {
                              width: 100%;
                              height: 100%;
                              object-fit: contain;
                        }
                  }
            }
      }

      &__description {
            box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
            border-radius: 0.5em;
            width: 80%;
            margin: auto;
            color: #fff;

            @media screen and (max-width: 769px) {
                  margin-top: 2em;
            }

            @media screen and (max-width: 550px) {
                  width: 90%;
            }

            h1 {
                  font-size: 2em;

                  @media screen and (max-width: 769px) {
                        font-size: 1.3em;
                  }

                  @media screen and (max-width: 550px) {
                        //font-family: "Great Vibes", cursive;
                        font-size: 1.2em;
                        font-weight: 600;
                  }
            }

            p {
                  @media screen and (max-width: 769px) {
                        //font-family: Arial, Helvetica, sans-serif;
                        //font-family: 'Courier New', Courier, monospace;
                        font-size: 1em;
                  }

                  @media screen and (max-width: 550px) {
                        font-family: "Roboto", sans-serif;
                        //font-size: 0.5em;
                  }
            }
      }

      &__video {
            width: 60%;
            height: auto;
            margin: auto;
            margin-bottom: 2em;
            object-fit: cover;

            @media screen and (max-width: 769px) {
                  width: 80%;
            }

            @media screen and (max-width: 550px) {
                  width: 90%;
                  margin-top: 1em;
            }

            video {
                  width: 100%;
                  height: 100%;
            }
      }

      &__gallery {
            width: 85%;
            margin: auto;
            max-height: 95%;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;

            @media screen and (max-width: 769px) {
                  //width: 90%;
                  display: grid;
                  grid-template-columns: repeat(2, 1fr);
            }

            @media screen and (max-width: 550px) {
                  grid-template-columns: repeat(1, 1fr);
                  width: 90%;
                  margin: auto;
            }

            &--text {
                  display: none;
            }

            &--items {
                  padding: 0.5em;
                  max-height: 100%;
                  position: relative;

                  @media screen and (max-width: 550px) {
                        //width: 90%;
                        //margin: auto;
                        position: relative;
                        //border: solid 3px saddlebrown;
                  }

                  img {
                        border-radius: 0.5em;
                        width: 300px;
                        height: 200px;

                        @media screen and (max-width: 550px) {
                              width: 90%;
                              //height: auto;
                              //height: auto;
                              margin: auto;
                              object-fit: cover;
                        }
                  }

                  .items_ping_pong {
                        @media screen and (max-width: 550px) {
                              //top: 21em;
                        }
                  }

                  div {
                        position: absolute;
                        cursor: pointer;
                        top: 6px;
                        width: 95%;
                        height: 94%;
                        opacity: 0;
                        transition: all 0.5s ease-in-out;

                        @media screen and (max-width: 769px) {
                              position: absolute;
                              top: 10.4em;
                              //bottom: 5em;
                              height: 20%;
                              width: 94%;
                              opacity: 1;
                        }

                        @media screen and (max-width: 550px) {
                              top: 11em;
                              width: 87%;
                              transform: translateX(0.9em);
                              height: 15%;
                              //border: solid 3px rgb(27, 130, 27);
                        }

                        @media screen and (max-width: 376px) {
                              transform: translateX(1em);
                        }

                        &:hover {
                              opacity: 1;
                              //
                              h2 {
                                    transform: translateY(0%);
                                    transition: 0.5s;
                                    text-align: left;
                              }
                        }

                        //
                        h2 {
                              font-size: 1.5em;
                              color: #fff;
                              height: 100%;
                              display: flex;
                              align-items: center;
                              justify-content: center;
                              transform: translateY(100%);
                              border-radius: 0.5em;
                              background: rgba(0, 0, 0, 0.5);
                              font-family: "Great Vibes", cursive;
                              font-size: 2rem;
                              text-align: left;

                              @media screen and (max-width: 769px) {
                                    transform: translateY(0);
                                    font-size: 1.5em;
                                    border-radius: 0.1em;
                              }

                              .plus {
                                    font-size: 1.5em;
                                    display: block;
                                    margin: 0 1em;

                                    @media screen and (max-width: 769px) {
                                          display: none;
                                    }

                                    &:hover {
                                          font-size: 1.7em;
                                          margin: 0 0.5em;

                                          .title {
                                                text-align: left;
                                          }
                                    }
                              }
                        }
                  }
            }
      }

      &__popup {
            position: fixed;
            top: 0;
            left: 0;
            height: 100%;
            width: 100%;
            z-index: 100000;
            display: none;
            transition: 0.5s ease-in-out;
            backdrop-filter: contrast(40%) brightness(90%) blur(10px);

            div {
                  @media screen and (max-width: 769px) {
                        display: block;
                        width: 90%;
                        margin: 0.5em auto;
                  }

                  @media screen and (max-width: 550px) {
                        //display: block;
                        width: 98%;
                        //margin: 0.5em auto;
                  }
            }

            &--main {
                  position: absolute;
                  top: 50%;
                  left: 50%;
                  transform: translate(-50%, -50%);

                  @media screen and (max-width: 769px) {
                        transform: translate(-50%, -53%);
                  }

                  @media screen and (max-width: 550px) {
                        transform: translate(-50%, -55%);
                  }
            }

            span {
                  position: absolute;
                  top: 0;
                  right: 10px;
                  font-size: 100px;
                  font-weight: bolder;
                  color: #fff;
                  cursor: pointer;
                  z-index: 100000;

                  @media screen and (max-width: 769px) {
                        font-size: 50px;
                  }
            }

            img {
                  object-fit: cover;
                  display: flex;
                  justify-content: center;
                  align-items: center;
            }

            &--paragraph {
                  display: flex;
                  justify-content: center;
                  align-items: center;
                  background: rgba(255, 255, 255, 0.8);
                  border-radius: 0.5rem;
                  font-family: "Great Vibes", cursive;
                  font-size: 2rem;
                  text-align: left;
                  padding-left: 1rem;
            }
      }
}
</style>
