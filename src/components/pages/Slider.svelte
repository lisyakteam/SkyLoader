<script>
  export let selected;
  export let versions = ["1.21.8", "1.21.7", "1.20.2", "1.19.4"];
  
  function prev() {
    const idx = versions.indexOf(selected);
    selected = versions[(idx - 1 + versions.length) % versions.length];
  }

  function next() {
    const idx = versions.indexOf(selected);
    selected = versions[(idx + 1) % versions.length];
  }
</script>

<style>
  .slider {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
  }
  .slider button {
    background: #444;
    color: #fff;
    border: none;
    padding: 5px 10px;
    border-radius: 6px;
    cursor: pointer;
  }
  .slider .version-display {
    min-width: 100px;
    text-align: center;
    font-weight: bold;
  }
</style>

<div class="slider">
  <button on:click={prev}>‹</button>
  <div class="version-display">{selected}</div>
  <button on:click={next}>›</button>
</div>

