<template>
    <div class="card">
        <h3>{{ post.Outpost_ID }}</h3>
    
        <!-- Use flexbox layout to display info-line divs horizontally -->
        <div class="info-container">
            <div class="info-line">
        <span class="label">Wallet mining rewards:</span>
        <span class="value">{{ post["Total wallet mining rewards"] }} dollar</span>
      </div> 
      <div class="info-line">
        <span class="label">Wallet royalties:</span>
        <span class="value">{{ post["Total wallet royalties"] }} ada</span>
      </div> 
      <div class="info-line">
        <span class="label">Wallet ecosystem fees:</span>
        <span class="value">{{ post["Total wallet ecosystem fees"] }} ada</span>
      </div> 
      <div class="info-line">
        <span class="label">Wallet derp rewards:</span>
        <span class="value">{{ post["Total wallet derp rewards"] }} $derp / epoch</span>
      </div> 

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
/* Add CSS to style the info-container */
.info-container {
    display: flex;
}

/* Adjust margin between info-line items */
.info-line {
    margin-right: 20px; /* Adjust as needed */
}

/* Adjust margin between info-line items */
.totals-wallet {
    margin-bottom: 20px; /* Adjust as needed */
}
</style>


