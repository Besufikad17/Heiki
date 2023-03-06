<script>
  import Header from "./lib/Header.svelte";
  import Footer from "./lib/Footer.svelte";
  import Card from "./lib/Card.svelte";

  const default_imgs = [
    "Classic",
    "Stinger",
    "Bulldog",
    "Marshal",
    "Shorty",
    "Spectre",
    "Guardian",
    "Operator",
    "Frenzy",
    "Bucky",
    "Phantom",
    "Ares",
    "Ghost",
    "Judge",
    "Vandal",
    "Odin"
  ];
</script>
<link href='https://fonts.googleapis.com/css?family=Merriweather' rel='stylesheet'>

<main>
  <Header />
  <div class="container">
    <div class="row">
      {#each default_imgs as pic}
        <Card img="src/assets/{pic}.webp" name={pic} />
      {/each}
      <Card img="src/assets/Sheriff.webp" name="Sheriff" />
      <div />
      <div />
      <Card img="src/assets/TacticalKnife.webp" name="Knife" />
    </div>
    <br />
  </div>
  <Footer />
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
    grid-template-columns: repeat(4, 200px);
    grid-gap: 30px;
    margin: 10px 10px;
    padding: 20px 20px;
    background-color: #141e29;
  }

  @media (max-width: 800px) {
    .row {
      grid-template-columns: repeat(1, 250px);
    }
  }
</style>
