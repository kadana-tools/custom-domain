<template>
    <div class="cards-container" v-if="posts.length > 0">
      <!-- Render the rest of the items using v-for -->
      <div v-for="(post, index) in posts.slice(2)" :key="index" class="card">
        <h3>{{ post.Outpost_ID }}</h3>
  
        <!-- <div class="info-line">
          <img loading= "lazy" :src="post.Image" alt="Outpost Image" srcset="/image.png?width=100 100w" class="image">
        </div>  -->

        <div class="info-line">
          <img loading="lazy" :src="post.Image" alt="Outpost Image" :srcset="generateSrcset(post.Image)" class="image">
        </div>

        <!-- <div class="info-line">
          <span class="label">Size:</span>
          <span class="value">{{ post["Size"] }}</span>
        </div>  -->
        <div class="info-line">
          <span class="label">Faction:</span>
          <span class="value">{{ post["Faction"] }}</span>
        </div>   
        <!-- <div class="info-line">
          <span class="label">Location:</span>
          <span class="value">{{ post["Location"] }}</span>
        </div>    -->
        <div class="info-line">
          <span class="label">Mining Rewards:</span>
          <span class="value">{{ post["MiningRewards"] }} ada</span>
        </div>  
        <div class="info-line" v-if="post.DerpRewards">
          <span class="label">Derp Rewards:</span>
          <span class="value">{{ post["DerpRewards"] }} $derp / epoch</span>
        </div>  
        <div class="info-line" v-if="post.EcosystemFees">
          <span class="label">Ecosystem Fees:</span>
          <span class="value">{{ post["EcosystemFees"] }} ada</span>
        </div>
        <div class="info-line" v-if="post.Royalties">
          <span class="label">Royalties:</span>
          <span class="value">{{ post["Royalties"] }} ada</span>
        </div>


      </div>
    </div>
</template>
  

<script>
export default {
  props: {
    posts: {
      type: Array,
      default: () => [] // Default value for posts if not provided by the parent
    }
  },
  methods: {
    generateSrcset(imageUrl) {
      // Generate different sizes of the image
      const imageSizes = [100, 200, 400]; // Add more sizes as needed
      const srcset = imageSizes.map(size => `${imageUrl}?width=${size} ${size}w`).join(', ');
      return srcset;
    }
  }
};
</script>



  