<script>
  import Card from "./Card.svelte";
  import axios from "axios";
  import { onMount } from "svelte";
  import { currentWeapon } from "./store";

  let weapon = $currentWeapon;
  let isLoading = true;
  let skins = [];
  let API_URL = import.meta.env.VITE_API_URL;

  const fetch = async() => {
    axios.get(`${API_URL}/api/type/${weapon}`).then(res => {
        console.log(res.data);
        skins = [...skins, res.data.data]
    }).catch(e => {
        console.log(e);
    })
  }

  onMount(async () => {
    fetch();
    // isLoading = false;
  });

</script>

<main>
  <div class="container">
   {#if isLoading}
    <div>
      Loading....
    </div>
    {:else}
      <div class="row">
        {#each skins as skin}
            <Card img="" name="" />
        {/each}
      </div>
   {/if}
  </div>
</main>

<style>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
    padding: 20px 20px;
  }

  .row {
    display: grid;
    grid-template-columns: repeat(3, 200px);
    grid-gap: 30px;
    margin: 10px 10px;
    padding: 20px 20px;
  }

  @media (max-width: 800px) {
    .row {
      grid-template-columns: repeat(1, 250px);
    }
  }
</style>
