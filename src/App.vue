<template>
  <div id="grid">
    <div id="A8" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A8
    </div>
    <div id="B8" class="square even" @drop.prevent="drop" @dragover.prevent>
      B8
    </div>
    <div id="C8" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C8
    </div>
    <div id="D8" class="square even" @drop.prevent="drop" @dragover.prevent>
      D8
    </div>
    <div id="E8" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E8
    </div>
    <div id="F8" class="square even" @drop.prevent="drop" @dragover.prevent>
      F8
    </div>
    <div id="G8" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G8
    </div>
    <div id="H8" class="square even" @drop.prevent="drop" @dragover.prevent>
      H8
    </div>

    <div id="A7" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A7
      <img
        id="A7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="B7" class="square even" @drop.prevent="drop" @dragover.prevent>
      B7
      <img
        id="B7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="C7" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C7
      <img
        id="C7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="D7" class="square even" @drop.prevent="drop" @dragover.prevent>
      D7
      <img
        id="D7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="E7" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E7
      <img
        id="E7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="F7" class="square even" @drop.prevent="drop" @dragover.prevent>
      F7
      <img
        id="F7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="G7" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G7
      <img
        id="G7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>
    <div id="H7" class="square even" @drop.prevent="drop" @dragover.prevent>
      H7
      <img
        id="H7pawn"
        src="https://static.vecteezy.com/system/resources/thumbnails/010/954/466/small/chess-pawn-icon-free-vector.jpg"
        width="50"
        height="50"
        draggable="true"
        @dragstart="drag"
      />
    </div>

    <div id="A6" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A6
    </div>
    <div id="B6" class="square even" @drop.prevent="drop" @dragover.prevent>
      B6
    </div>
    <div id="C6" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C6
    </div>
    <div id="D6" class="square even" @drop.prevent="drop" @dragover.prevent>
      D6
    </div>
    <div id="E6" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E6
    </div>
    <div id="F6" class="square even" @drop.prevent="drop" @dragover.prevent>
      F6
    </div>
    <div id="G6" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G6
    </div>
    <div id="H6" class="square even" @drop.prevent="drop" @dragover.prevent>
      H6
    </div>

    <div id="A5" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A5
    </div>
    <div id="B5" class="square even" @drop.prevent="drop" @dragover.prevent>
      B5
    </div>
    <div id="C5" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C5
    </div>
    <div id="D5" class="square even" @drop.prevent="drop" @dragover.prevent>
      D5
    </div>
    <div id="E5" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E5
    </div>
    <div id="F5" class="square even" @drop.prevent="drop" @dragover.prevent>
      F5
    </div>
    <div id="G5" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G5
    </div>
    <div id="H5" class="square even" @drop.prevent="drop" @dragover.prevent>
      H5
    </div>

    <div id="A4" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A4
    </div>
    <div id="B4" class="square even" @drop.prevent="drop" @dragover.prevent>
      B4
    </div>
    <div id="C4" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C4
    </div>
    <div id="D4" class="square even" @drop.prevent="drop" @dragover.prevent>
      D4
    </div>
    <div id="E4" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E4
    </div>
    <div id="F4" class="square even" @drop.prevent="drop" @dragover.prevent>
      F4
    </div>
    <div id="G4" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G4
    </div>
    <div id="H4" class="square even" @drop.prevent="drop" @dragover.prevent>
      H4
    </div>

    <div id="A3" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A3
    </div>
    <div id="B3" class="square even" @drop.prevent="drop" @dragover.prevent>
      B3
    </div>
    <div id="C3" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C3
    </div>
    <div id="D3" class="square even" @drop.prevent="drop" @dragover.prevent>
      D3
    </div>
    <div id="E3" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E3
    </div>
    <div id="F3" class="square even" @drop.prevent="drop" @dragover.prevent>
      F3
    </div>
    <div id="G3" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G3
    </div>
    <div id="H3" class="square even" @drop.prevent="drop" @dragover.prevent>
      H3
    </div>

    <div id="A2" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A2
    </div>
    <div id="B2" class="square even" @drop.prevent="drop" @dragover.prevent>
      B2
    </div>
    <div id="C2" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C2
    </div>
    <div id="D2" class="square even" @drop.prevent="drop" @dragover.prevent>
      D2
    </div>
    <div id="E2" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E2
    </div>
    <div id="F2" class="square even" @drop.prevent="drop" @dragover.prevent>
      F2
    </div>
    <div id="G2" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G2
    </div>
    <div id="H2" class="square even" @drop.prevent="drop" @dragover.prevent>
      H2
    </div>

    <div id="A1" class="square odd" @drop.prevent="drop" @dragover.prevent>
      A1
    </div>
    <div id="B1" class="square even" @drop.prevent="drop" @dragover.prevent>
      B1
    </div>
    <div id="C1" class="square odd" @drop.prevent="drop" @dragover.prevent>
      C1
    </div>
    <div id="D1" class="square even" @drop.prevent="drop" @dragover.prevent>
      D1
    </div>
    <div id="E1" class="square odd" @drop.prevent="drop" @dragover.prevent>
      E1
    </div>
    <div id="F1" class="square even" @drop.prevent="drop" @dragover.prevent>
      F1
    </div>
    <div id="G1" class="square odd" @drop.prevent="drop" @dragover.prevent>
      G1
    </div>
    <div id="H1" class="square even" @drop.prevent="drop" @dragover.prevent>
      H1
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    // allowDrop(event) {
    //   console.log(event);
    // },
    drag(event) {
      event.dataTransfer.setData("text", event.target.id);
    },
    drop(event) {
      let data = event.dataTransfer.getData("text");
      event.target.appendChild(document.getElementById(data));
    },
  },
};
</script>

<style>
#grid {
  display: inline-grid;
  grid-template-columns: repeat(8, minmax(0, 1fr));
  column-gap: 0;
}
.square {
  border-style: solid;
  border-width: 2px;
  text-align: center;
  height: 50px;
  width: 50px;
}
@media (width >= 600px) and (height >= 600px) {
  .square {
    height: 75px;
    width: 75px;
  }
}
@media (width >= 800px) and (height >= 800px) {
  .square {
    height: 100px;
    width: 100px;
  }
}

.odd {
  background-color: white;
}
.even {
  background-color: grey;
}
</style>
