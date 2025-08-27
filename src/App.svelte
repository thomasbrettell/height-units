<script>
  let percentHeigt;
  let vhHeight;
  let dvhHeight;
  let lvhHeight;
  let svhHeight;
  let windowInnerHeight;
  let windowOuterHeight;
</script>

<svelte:window
  bind:innerHeight={windowInnerHeight}
  bind:outerHeight={windowOuterHeight}
/>

<div bind:clientHeight={percentHeigt} class="sizer percent" />
<div bind:clientHeight={vhHeight} class="sizer vh" />
<div bind:clientHeight={dvhHeight} class="sizer dvh" />
<div bind:clientHeight={lvhHeight} class="sizer lvh" />
<div bind:clientHeight={svhHeight} class="sizer svh" />

<div style:position="fixed" style:left="0" style:top="0">
  <p>100% = {percentHeigt}px</p>
  <p>100vh = {vhHeight}px</p>
  <p>100dvh = {dvhHeight}px</p>
  <p>100lvh = {lvhHeight}px</p>
  <p>100svh = {svhHeight}px</p>
  <p>window.innerHeight = {windowInnerHeight}px</p>
  <p>window.outerHeight = {windowOuterHeight}px</p>
</div>

<style>
  p {
    margin: 0;
  }

  .sizer {
    position: fixed !important;
    top: 0;
    left: 0;
    width: 100%;
    user-select: none;
    pointer-events: none;
    opacity: 0;
  }

  .sizer.percent {
    height: 100%;
  }

  .sizer.vh {
    height: 100vh;
  }

  .sizer.dvh {
    height: 100dvh;
  }

  .sizer.lvh {
    height: 100lvh;
  }

  .sizer.svh {
    height: 100svh;
  }
</style>
