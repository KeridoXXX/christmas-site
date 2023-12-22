<template>
  <div>
    <header></header>

    <main>
      <div class="jule-grid">
        <div>
          <div class="welc">
            <h1>Julemanden er webudvikler!</h1>
            <h2>Og jeg har glemt at købe julegaver til...</h2>
            <ul>
              <li>Mor Mai</li>
              <li>Søde Sus</li>
              <li>Hyggemand</li>
              <li>Lillebror</li>
              <li>Gitte</li>
            </ul>
            <p>
              Jeg har lavet jer en lille digital julegave i stedet <br />
              I skal blot ha den rigtige adgangskode for at få adgang til jeres
              julegave:
            </p>
          </div>
          <div>
            <input v-model="password" placeholder="Enter password" />
            <button @click="submitPassword">Submit</button>
          </div>
        </div>

        <div class="gift-cont" v-if="passwordCorrect">
          <!-- Render the selected component based on the user -->
          <div v-if="selectedUser === 'mor-mai'">
            <h3>Kære mor - glædelig jul</h3>
            <p>
              Beklager at min gave kommer sådan her, jeg printer den så snart så
              muligt og elsker dig
            </p>
            <img :src="morSmallImage" alt="Mor Small Image" />
            <p>*Der er andre farver tilgængelige</p>
          </div>
          <div v-if="selectedUser === 'mor-sus'">
            <h3>Kære Sus - glædelig jul</h3>
            <p>
              Jeg er glad for at jeg må være med igen i år, og mange tak for
              lækker mad
            </p>
            <img :src="susSmallImage" alt="Sus Small Image" />
            <p>*Der er andre farver tilgængelige</p>
          </div>
          <div v-if="selectedUser === 'hjalmar'">
            <h3>Glædelig jul Perk</h3>
            <p>Der vil gå en moderat mænge år før du kan stå imod mig</p>
            <p>
              Her er en lille gave fra Marius og Sylvester - den findes ikke
              endnu, men vi laver den ægte så snart så muligt
            </p>
            <img :src="perkSmallImage" alt="hjalmar Small Image" />
            <p>*Der er andre farver tilgængelige</p>
          </div>
          <div v-if="selectedUser === 'vilhelm'">
            <h3>Glædelig jul Jenkins</h3>
            <p>Der er ingen respekt for riddere</p>
            <p>
              Her er en lille gave fra Marius og Sylvester - den findes ikke
              endnu, men vi laver den ægte så snart så muligt
            </p>
            <img :src="lefleSmallImage" alt="vilhelm Small Image" />
            <p>*Der er andre farver tilgængelige</p>
          </div>
          <div v-if="selectedUser === 'mor-gitte'">
            <h3>Glædelig jul søde Gitte</h3>
            <p>Tak fordi du er sød og rar</p>
            <img :src="morSmallImage" alt="Gittemor Small Image" />
            <p>*Der er andre farver tilgængelige</p>
          </div>
        </div>
      </div>
    </main>

    <footer></footer>
  </div>
</template>

<script>
import morSmallImage from "@/assets/mor-small.webp";
import susSmallImage from "@/assets/sus-small.webp";
import lefleSmallImage from "@/assets/lefle-small.webp";
import perkSmallImage from "@/assets/perk-small-green.webp";

export default {
  data() {
    return {
      password: "",
      passwordCorrect: false,
      selectedUser: null,
      morSmallImage,
      susSmallImage,
      lefleSmallImage,
      perkSmallImage,
      // Define passwords for each user
      passwords: {
        "mor-mai": "madsen",
        "mor-sus": "nøddepostej",
        hjalmar: "morgenæg",
        vilhelm: "bulgarien",
        "mor-gitte": "gittemor",
      },
    };
  },
  methods: {
    submitPassword() {
      // Check if the entered password is correct for any user
      for (const user in this.passwords) {
        if (this.password === this.passwords[user]) {
          this.passwordCorrect = true;
          this.selectedUser = user;
          return; // Exit the loop if a match is found
        }
      }
      // Handle incorrect password
      alert("Incorrect password. Please try again.");
    },
  },
};
</script>

<style scoped>
img {
  max-width: 100%;
}
.jule-grid {
  margin: 1rem;
  display: grid;
  gap: 2rem;
}

.gift-cont {
  max-width: 100vw;
}
/* Your styles go here */
</style>
