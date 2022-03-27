<script>
  export let width = '180px';
  export let height = '320px';
  export let is3d = false;
  export let isVertical = false;
</script>

<style>
  .flipcard {
  }

  .flipcard-3d {
    perspective: 9000px;
  }

  .flipcard-inner {
    position: relative;
    width: 100%;
    height: 100%;
    transition: transform .3s linear;
    transform-style: preserve-3d;
  }

  .flipcard:hover .flipcard-inner {
    transform: rotateY(180deg);
  }

  .flipcard-vertical:hover .flipcard-inner {
    transform: rotateX(180deg);
  }

  .flipcard-front,
  .flipcard-back {
    position: absolute;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  .flipcard-front {
    background-color: red;
  }

  .flipcard .flipcard-back {
    background-color: green;
    transform: rotateY(180deg);
  }

  .flipcard-vertical .flipcard-back {
    background-color: green;
    transform: rotateX(180deg);
  }
</style>

<div class="flipcard"
     class:flipcard-3d="{is3d}"
     class:flipcard-vertical="{isVertical}"
     style="width: {width}; height: {height}"
     >
  <div class="flipcard-inner">
    <div class="flipcard-front">
      <slot name="front" />
    </div>
    <div class="flipcard-back">
      <slot name="back" />
    </div>
  </div>
</div>
