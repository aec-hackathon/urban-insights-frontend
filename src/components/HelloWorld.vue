<template>
  <v-container id="app">
    <v-layout text-xs-center wrap>
      <v-flex xs12 id="logo">
        <v-img :src="require('../assets/logo.png')" class="my-3" contain height="200"></v-img>
      </v-flex>

      <v-flex mb-4>
        <h1 class="display-2 font-weight-bold mb-3">Urban Insights</h1>
        <p
          class="subheading font-weight-regular"
        >An application for visualizing proposed buildings, their code-constraints, and overlay analyses using AR & VR.
          <!-- <a
            href="https://github.com/mitevpi/urban-insights-frontend"
            target="_blank"
          >GitHub</a>-->
        </p>
      </v-flex>

      <v-flex mb-5 xs12>
        <h2 class="headline font-weight-bold mb-3">Development</h2>

        <v-layout justify-center>
          <a
            v-for="(next, i) in whatsNext"
            :key="i"
            :href="next.href"
            class="subheading mx-3"
            target="_blank"
          >{{ next.text }}</a>
        </v-layout>
      </v-flex>

      <v-flex xs12 mb-5>
        <h2 class="headline font-weight-bold mb-3">Links</h2>

        <v-layout justify-center>
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >{{ link.text }}</a>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    importantLinks: [
      {
        text: "Presentation",
        href:
          "https://drive.google.com/open?id=1z9CS6sx12UACRg9ft4Z1L9axQsGe2ao_dAfdpk4cB9w"
      },
      {
        text: "Technical Questions",
        href: "https://github.com/mitevpi"
      }
    ],
    whatsNext: [
      {
        text: "Frontend GitHub",
        href: "https://github.com/mitevpi/urban-insights-frontend"
      },
      {
        text: "Backend GitHub",
        href: "https://github.com/mitevpi/urban-insights-backend"
      }
    ]
  })
};
</script>

<style scoped>
#app {
  overflow: hidden;
}

#logo {
  margin-top: 3%;
}
</style>
