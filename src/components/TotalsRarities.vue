<template>
    <div class="card">
        <h3>{{ post.Outpost_ID }}</h3>
    
        <!-- Use flexbox layout to display info-line divs horizontally -->
        <div class="info-container">
            <div class="info-line">
                <span class="label">Commons:</span>
                <span class="value">{{ post["Commons"] }}</span>
            </div> 
            <div class="info-line">
                <span class="label">Uncommons:</span>
                <span class="value">{{ post["Uncommons"] }}</span>
            </div> 
            <div class="info-line">
                <span class="label">Rares:</span>
                <span class="value">{{ post["Rares"] }}</span>
            </div> 
            <div class="info-line">
                <span class="label">Epics:</span>
                <span class="value">{{ post["Epics"] }}</span>
            </div> 
            <div class="info-line">
                <span class="label">Legendaries:</span>
                <span class="value">{{ post["Legendaries"] }}</span>
            </div> 
            <div class="info-line">
                <span class="label">Mythicals:</span>
                <span class="value">{{ post["Mythicals"] }}</span>
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
.totals-rarities {
    margin-bottom: 20px; /* Adjust as needed */
}
</style>


