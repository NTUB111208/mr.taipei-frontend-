<template>
  <div>
    <div style="height: 100vh">
      <client-only>
        <l-map :zoom="15" :center="[25.0462897, 121.5166667]">
          <l-tile-layer
            url="https://tiles.stadiamaps.com/tiles/alidade_smooth_dark/{z}/{x}/{y}{r}.png"
          ></l-tile-layer>
          <l-marker :lat-lng="[25.0462897, 121.5166667]"></l-marker>
        </l-map>
      </client-only>
    </div>
    <div class="wrapper">
      <nuxt />
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.wrapper {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 1rem;

  z-index: 1000;

  width: 100%;
  height: 100%;
  box-sizing: border-box;

  display: flex;
  justify-content: center;
  align-items: flex-end;
}
</style>
