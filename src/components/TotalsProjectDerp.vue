<template>
    <div class="card">
      <h3>{{ post.Outpost_ID }}</h3>
  
      <div class="info-line">
        <span class="label">Project mining rewards:</span>
        <span class="value">{{ post["Total project mining rewards"] }} dollar</span>
      </div> 
      <div class="info-line">
        <span class="label">Project royalties:</span>
        <span class="value">{{ post["Total project royalties"] }} ada</span>
      </div> 
      <div class="info-line">
        <span class="label">Project ecosystem fees:</span>
        <span class="value">{{ post["Total project ecosystem fees"] }} ada</span>
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
.total-project {
  margin-bottom: 20px; /* Adjust the margin as needed */
}
</style>