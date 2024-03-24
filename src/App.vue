<template>
  <div class="container">
    <form @submit.prevent="fetchPost" class="form-container">
      <div>
        <label for="address" class="label"></label>
        <input
          type="text"
          id="address"
          v-model="formData.address"
          class="input-field"
          placeholder="Enter your wallet address or $handle..."
        />
      </div>
      <button type="submit" class="submit-button">Get my warriors!</button>
    </form>

    <!-- Render the first item using the Totals component -->
    <Totals :post="posts[0]" v-if="posts[0]" class="total-totals" />

    <TotalsRarities :post="posts[1]" v-if="posts[1]" class="totals-rarities" />

    <Containers :posts="posts" />   
    
    <hr />   
  </div>
</template>

<script>
import axios from "axios";
import Totals from "./components/Totals.vue"; // Import the Total component
import TotalsRarities from "./components/TotalsRarities.vue"; // Import the Total component
import Containers from "./components/Containers.vue"; // Import the Containers component


export default {
  components: {
    Totals, // Register the Totals component
    TotalsRarities, 
    Containers // Register the Containers component
  },
  data() {
    return {
      formData: {
        address: "",
      },
      posts: [],
    };
  },
  methods: {
    async fetchPost() {
      try {
        const response = await axios.post(
          "https://kadana-incl-totals.ew.r.appspot.com/get_metadata",
          this.formData
        );
        this.posts = response.data;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>


<style>
html,
body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}

.image {
  max-width: 200px; /* Adjust the max-width as needed */
  max-height: 200px; /* Adjust the max-height as needed */
}

.container {
  box-sizing: border-box;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  /* padding: 20px; */
  background-image: url("https://cardanowarriors.io/assets/warriors-3b868c33.png");
  background-size: cover;
  background-position: center;
}

.loading {
  color: white;
  font-size: 24px;
  margin-top: 20px;
}

.form-container {
  width: 100%;
  max-width: 400px;
  margin-top: 20px;
  margin-bottom: 20px;
}

.input-field {
  width: calc(100% - 24px);
  padding: 12px;
  margin-bottom: 10px;
  border: none;
  border-radius: 8px;
  background-color: rgba(255, 255, 255, 0.7);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.input-field::placeholder {
  color: #666666c0;
}

.submit-button {
  width: calc(100% - 24px);
  padding: 12px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.submit-button:hover {
  background-color: #45a049;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
  max-height: calc(100vh - 200px);
  overflow-y: auto;
}

.card {
  /* existing card styles */
  background-color: rgba(255, 255, 255, 0.7); /* Add this line */
  padding: 10px;
}

.info-line {
  display: flex;
  align-items: center;
  margin-bottom: 5px;
}

.label {
  font-weight: bold;
  margin-right: 5px;
}

.value {
  flex-grow: 1;
}


.card h3 {
  margin-bottom: 10px;
  color: #333333;
}

.card p {
  color: #666;
}

hr {
  margin-top: 20px;
  border: none;
  border-top: 1px solid #ddd;
  width: 100%;
}

</style>
