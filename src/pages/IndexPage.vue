<template>
  <q-page class="flex flex-center q-gutter-lg">
    <div id="particles-js"></div>
    <div
      class="animated bounceInUp"
      v-bind:style="
        $q.screen.lt.sm
          ? { width: '90%', 'padding-top': '100px' }
          : { width: '35%' }
      "
    >
      <q-card class="bg-white">
        <q-card-section>
          <q-avatar size="200px" class="absolute-center shadow-19">
            <img class="circle" :src="logo" />
          </q-avatar>
        </q-card-section>
        <q-card-section
          class="text-black"
          style="padding-top: 100px; text-align: center"
        >
          <div class="row justify-center">
            <div class="col-12 col-md-auto">
              <div class="text-h5 text-bold ft">{{ name }}</div>
            </div>
            <div class="col-12 col-md-auto">
              <p class="text-subtitle2 text-grey-5">
                {{ position }}
              </p>
            </div>
          </div>
        </q-card-section>
        <q-separator class="bg-grey-4" />
        <q-card-section class="text-black" style="text-align: center">
          <div class="row justify-center q-gutter-md">
            <q-btn
              @click="
                redirectToNetwork(
                  'https://www.linkedin.com/in/alejandro-casta%C3%B1eda-ocampo-478420148'
                )
              "
              class="text-primary"
              size="md"
              round
              outline
            >
              <q-icon color="primary" name="fab fa-linkedin" size="1.2rem" />
            </q-btn>
            <q-btn
              @click="redirectToNetwork('https://github.com/4l3j4ndr0')"
              class="text-primary"
              size="md"
              round
              outline
            >
              <q-icon color="primary" name="fab fa-github" size="1.2rem" />
            </q-btn>
            <q-btn
              @click="
                redirectToNetwork('https://medium.com/@alejandro.casta3447')
              "
              class="text-primary"
              size="md"
              round
              outline
            >
              <q-icon color="primary" name="fab fa-medium" size="1.2rem" />
            </q-btn>
            <q-btn
              @click="redirectToNetwork('https://wa.link/jqango')"
              class="text-primary"
              size="md"
              round
              outline
            >
              <q-icon color="primary" name="fab fa-whatsapp" size="1.2rem" />
            </q-btn>
          </div>
        </q-card-section>
      </q-card>
    </div>
    <div
      class="animated bounceInUp"
      v-bind:style="$q.screen.lt.sm ? { width: '90%' } : { width: '35%' }"
    >
      <div class="bg-transparent" style="text-align: center">
        <q-img
          @click="redirectToNetwork(item.url)"
          v-for="item in certifications"
          style="width: 30%; height: 30%; cursor: pointer"
          :src="item.image"
        />
      </div>
    </div>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from "components/models";
import { defineComponent, ref, onMounted } from "vue";

export default defineComponent({
  name: "Index",
  setup() {
    const logo = new URL("../../image.png", import.meta.url).href;
    const name = "Alejandro Castaneda O.";
    const position = "Sr. Cloud Engineer & FullStack developer";
    const redirectToNetwork = (url: string) => {
      window.open(url);
    };
    onMounted(() => {
      particlesJS("particles-js", {
        particles: {
          number: {
            value: 80,
            density: {
              enable: true,
              value_area: 700,
            },
          },
          color: {
            value: "#ffffff",
          },
          shape: {
            type: "circle",
            stroke: {
              width: 0,
              color: "#000000",
            },
            polygon: {
              nb_sides: 5,
            },
          },
          opacity: {
            value: 0.5,
            random: false,
            anim: {
              enable: false,
              speed: 0.1,
              opacity_min: 0.1,
              sync: false,
            },
          },
          size: {
            value: 3,
            random: true,
            anim: {
              enable: false,
              speed: 10,
              size_min: 0.1,
              sync: false,
            },
          },
          line_linked: {
            enable: true,
            distance: 150,
            color: "#ffffff",
            opacity: 0.4,
            width: 1,
          },
          move: {
            enable: true,
            speed: 2,
            direction: "none",
            random: false,
            straight: false,
            out_mode: "out",
            bounce: false,
            attract: {
              enable: false,
              rotateX: 600,
              rotateY: 1200,
            },
          },
        },
        interactivity: {
          detect_on: "canvas",
          events: {
            onhover: {
              enable: true,
              mode: "grab",
            },
            onclick: {
              enable: true,
              mode: "push",
            },
            resize: true,
          },
          modes: {
            grab: {
              distance: 140,
              line_linked: {
                opacity: 1,
              },
            },
            bubble: {
              distance: 400,
              size: 40,
              duration: 2,
              opacity: 8,
              speed: 3,
            },
            repulse: {
              distance: 200,
              duration: 0.4,
            },
            push: {
              particles_nb: 4,
            },
            remove: {
              particles_nb: 2,
            },
          },
        },
        retina_detect: true,
      });
    });
    const certifications: any = [
      {
        image: new URL(
          "../../badges/aws-certified-solutions-architect-professional.png",
          import.meta.url
        ).href,
        url: "https://www.credly.com/badges/4f5ac3a7-daa3-4efc-a60b-a092d7479590/public_url",
      },
      {
        image: new URL(
          "../../badges/aws-solutions-architect-associate.png",
          import.meta.url
        ).href,
        url: "https://www.credly.com/badges/f031ad39-e90f-400c-8381-0e9e168d1f8d/public_url",
      },
      {
        image: new URL(
          "../../badges/aws-certified-developer-associate.png",
          import.meta.url
        ).href,
        url: "https://www.credly.com/badges/9812bf1c-9323-4e69-a5b4-d92142bf1329/public_url",
      },
      {
        image: new URL(
          "../../badges/aws-accreditation-technical.png",
          import.meta.url
        ).href,
        url: "https://www.credly.com/badges/14ffaaf3-913f-4c3b-9259-9da62a879d0f/public_url",
      },
      {
        image: new URL("../../badges/aws-object-storage.png", import.meta.url)
          .href,
        url: "https://www.credly.com/badges/a4b34cff-a0f1-499f-883c-ae2d68581e45/public_url",
      },
      {
        image: new URL(
          "../../badges/well-architected-proficient.png",
          import.meta.url
        ).href,
        url: "https://www.credly.com/badges/cbb33f9e-330c-4100-ac2d-d4addc744cb1/public_url",
      },
      {
        image: new URL(
          "../../badges/aws-partner-migration-ambassador-2023-business.png",
          import.meta.url
        ).href,
        url: "https://www.credly.com/badges/cc5ff5ed-0c50-47f2-9ad9-a77f335de725/public_url",
      },
      {
        image: new URL("../../badges/comunity_builder.png", import.meta.url)
          .href,
        url: "",
      },
    ];

    return {
      logo,
      name,
      position,
      redirectToNetwork,
      certifications,
    };
  },
});
</script>
<style>
.circle {
  background-color: rgb(249, 250, 248);
  border: 4px solid #fff;
  border-radius: 18px;
  box-shadow: 0 0 px #888;
  height: 30px;
  width: 30px;
}
#particles-js {
  position: absolute;
  width: 100%;
  height: 100%;
  background: linear-gradient(145deg, rgb(74, 94, 137) 15%, #030303 70%);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50% 50%;
}
</style>
