<script>
  import data from "../data/parks-data.json";
  const parks = data.data;

  const notImageAvilable =
    "data:image/jpeg;base64,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";

  function getImageUrl(park) {
    return park.images.length > 0 ? park.images[0].url : notImageAvilable;
  }

  function getAltText(park) {
    return park.images.length > 0
      ? park.images[0].altText
      : "Not image Available";
  }
</script>


<style>
    .grid-container {
      display: grid;
      grid-column-gap: 10px;
      grid-template-columns: auto auto;
      padding: 10px;
    }
    
    .grid-item {
      padding: 20px;
      font-size: 30px;
      text-align: center;
    }
 
    img {
  border-radius: 5px 5px 0 0;
}
    .card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px; /* 5px rounded corners */
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
}



</style>
    
    <h1>Parks</h1>
    <div class="grid-container">
        {#each parks as park}
        <div class="grid-item">
            <div class="card">
                <div class="container">
                    <img 
                    src="{getImageUrl(park)}" 
                    alt="{getAltText(park)}" 
                    style="width:100%">
                    <h4>
                        <b>{park.fullName}</b>
                    </h4>
                </div>
              </div>
        </div>
      {/each}
    </div>
    