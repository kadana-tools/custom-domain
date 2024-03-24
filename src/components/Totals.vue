<template>
    <div class="card">
      <h3>{{ post.Outpost_ID }}</h3>
  
      <div class="info-line">
        <span class="label">Total Warriors:</span>
        <span class="value">{{ post["Total_Warriors"] }}</span>
      </div> 
      <div class="info-line">
        <span class="label">Total WP:</span>
        <span class="value">{{ post["Total_WP"] }}</span>
      </div> 

    </div>
</template>
  
<script>
export default {
  props: {
    post: Object
  }
};
</script>

<style>
/* Add margin to the Totals component */
.total-totals {
  margin-bottom: 20px; /* Adjust the margin as needed */
}
</style>