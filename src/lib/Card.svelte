<script>
    export let img
    export let name
</script>

<main>
  <div class="container">
    <img src={img} alt="" />
    <p class="name">{name}</p>
  </div>
</main>

<style>
  .name {
    display: none;
    top: 50%;
    left: 50%;
    font-family: 'Merriweather';
    font-size: 11px;
    color: white;
  }

  .container:hover {
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    border-style: none;
    text-align: center;
    justify-content: center;
  }

  .container:hover .name {
    display: block;
  }

  .container img {
    width: auto;
    height: auto;
    object-fit: cover;
  }
</style>
