<template>
    <div class="cards-container" v-if="posts.length > 0">
      <!-- Render the rest of the items using v-for -->
      <div v-for="(post, index) in posts.slice(2)" :key="index" class="card">
        <h3>{{ post.Outpost_ID }}</h3>
  
        <div class="info-line">
          <img :src="post.Image" class="image" alt="Warrior Image">
        </div> 
        <div class="info-line">
          <span class="label">Name:</span>
          <span class="value">{{ post["Name"] }}</span>
        </div> 
        <div class="info-line">
          <span class="label">Type:</span>
          <span class="value">{{ post["Type"] }}</span>
        </div>   
        <div class="info-line">
          <span class="label">Rarity:</span>
          <span class="value">{{ post["Rarity"] }}</span>
        </div>   
        <div class="info-line">
          <span class="label">Warrior Points:</span>
          <span class="value">{{ post["WP"] }}</span>
        </div>  
      </div>
    </div>
</template>
  

<script>
export default {
  props: {
    posts: {
      type: Array,
      default: () => []
    }
  }
};
</script>


  