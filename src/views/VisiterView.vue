<template>
      <div class="visite" v-motion-pop>
            <div class="mb-16">
                  <div class="pt-20 paragraph">
                        <p class="bg-white bg-opacity-90">
                              <!--<span class="text-red-600 text-xl">!!!</span>-->
                              The path with the red marker is a dirt road. It is absolutely not drivable. Here are 2 examples of routes in blue.
                        </p>
                  </div>

                  <div class="flex justify-between pt-4 mb-10 visiter">
                        <div class="w-3/4 mr-2 ml-4 visiter__carte">
                              <iframe
                                    src="https://www.google.com/maps/d/u/0/embed?mid=11VwU5LYRymF8SbVfWczSPH-Zyrveu_w&ehbc=2E312F"
                                    width="100%"
                                    height="600"
                              ></iframe>
                        </div>

                        <div
                              class="bg-white bg-opacity-80 w-1/4 rounded-lg mr-1 visiter__description"
                        >
                              <h1 class="text-left ml-4">From the A13 :</h1>
                              <ol class="text-left ml-4">
                                    <li class="mb-4">
                                          Exit 25 "Bourg Achard: FECAMP, YVETOT, PONT de BROTONE"
                                    </li>

                                    <li class="mb-4">
                                          Continue on D313 towards FECAMP/YVETOT
                                    </li>

                                    <li class="mb-4">
                                          At the roundabout, turn left towards HAUVILLE
                                    </li>

                                    <li class="mb-4">
                                          From HAUVILLE (2 possibilities)
                                    </li>
                                    <li>
                                          <ul class="ml-10 mb-4">
                                                <li class="mb-4">
                                                      1- Once out of HAUVILLE,
                                                </li>
                                                <li class="mb-4">
                                                      At 1.5km, at the calvary, turn right
                                                </li>
                                                <li>Then take the 2nd right</li>
                                          </ul>

                                          <ul class="ml-10 mb-4">
                                                <li class="mb-4">
                                                      2- Keep right at the monument, then continue straight.
                                                </li>
                                                <li class="mb-4">
                                                      Once out of Hauville, turn left
                                                </li>

                                                <li class="mb-4">
                                                      Then take the 1st left
                                                </li>
                                          </ul>
                                    </li>

                                    <li>
                                          The entrance is at the end of the road, on the left, just before the dirt road.
                                    </li>
                              </ol>
                        </div>
                  </div>
            </div>

            <footer-view />
      </div>
</template>

<script>
import FooterView from "@/components/FooterView.vue";

export default {
      components: { FooterView },

      setup() {},
};
</script>

<style lang="scss" scoped>
.visite {
      transition: 0.25s ease-in;

      @media screen and (max-width: 769px) {
            margin-top: 1.5em;
            font-family: Arial, Helvetica, sans-serif;
      }

       @media screen and (max-width: 550px) {
            margin-top: 0em;
            //padding-top: 3em;
      }
}
.paragraph {
      width: 90%;
      margin: auto;
      text-align: justify;

      @media screen and (max-width: 769px) {
            width: 95%;
            margin-bottom: 1em;
      }

      p {
            padding: 1em;
            border-radius: 0.5em;

            span {
                  font-weight: bold;
                  //color: red;
            }
      }
}
.visiter {
      height: auto;

      @media screen and (max-width: 769px) {
            //border: 3px solid red;
            height: auto;
            display: block;
            //flex-direction: column-reverse;
            width: 95%;
            margin: 0 auto;
            padding-top: 0rem;
            //margin: 0;

      }

      @media screen and (max-width: 550px) {
            font-size: 0.9em;
            font-weight: 450;
      }

      &__carte {
            @media screen and (max-width: 769px) {
                  width: 100%;
                  margin: 0em;
            }
      }

      &__description {
            height: auto;

            @media screen and (max-width: 769px) {
                  width: 100%;
                  margin-bottom: 1em;
                  margin-top: 2em;
                  //font-size: 1em;
            }
            //width: 100%;
            //border: 3px solid blue;
            //margin: 0;
      }
}
</style>
