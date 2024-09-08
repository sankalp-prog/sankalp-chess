<template>
  <div id="grid">
    <div v-for="squareId in 64" :key="squareId">
      <div
        id=""
        class="square"
        :class="oddOrEven(squareId)"
        @drop.prevent="drop"
        @dragover.prevent
      >
        {{ squareId - 1}}
        <img
          v-if="chessBoard[squareId - 1].piece !== ''"
          :id="squareId"
          :src="getPieceImage(chessBoard[squareId - 1])"
          width="50"
          height="50"
          draggable="true"
          @dragstart="drag"
        />
      </div>
    </div>
  </div>
</template>
<!-- https://assets-themes.chess.com/image/ejgfv/150/bb.png  : Black Bishop-->
<!-- https://assets-themes.chess.com/image/ejgfv/150/bn.png  : Black Knight -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/bk.png  : Black King-->
<!-- https://assets-themes.chess.com/image/ejgfv/150/bq.png : Black Queen -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/bp.png  : Black Pawn -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/br.png : Black Rook-->

<!-- https://assets-themes.chess.com/image/ejgfv/150/wb.png -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/wk.png -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/wn.png -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/wp.png -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/wq.png -->
<!-- https://assets-themes.chess.com/image/ejgfv/150/wr.png -->

<script>
function coordinates(squareId) {
  const row = Math.ceil(squareId / 8);
  const column = squareId % 8;
  return [row, column];
}

const blackImages = {
  bishop: "https://assets-themes.chess.com/image/ejgfv/150/bb.png",
  knight: "https://assets-themes.chess.com/image/ejgfv/150/bn.png",
  king: "https://assets-themes.chess.com/image/ejgfv/150/bk.png",
  queen: "https://assets-themes.chess.com/image/ejgfv/150/bq.png",
  pawn: "https://assets-themes.chess.com/image/ejgfv/150/bp.png",
  rook: "https://assets-themes.chess.com/image/ejgfv/150/br.png",
};

const whiteImages = {
  bishop: "https://assets-themes.chess.com/image/ejgfv/150/wb.png",
  knight: "https://assets-themes.chess.com/image/ejgfv/150/wn.png",
  king: "https://assets-themes.chess.com/image/ejgfv/150/wk.png",
  queen: "https://assets-themes.chess.com/image/ejgfv/150/wq.png",
  pawn: "https://assets-themes.chess.com/image/ejgfv/150/wp.png",
  rook: "https://assets-themes.chess.com/image/ejgfv/150/wr.png",
};

export default {
  data() {
    return {
      chessBoard: [
        {
          piece: "rook",
          player: "black",
        },
        {
          piece: "knight",
          player: "black",
        },
        {
          piece: "bishop",
          player: "black",
        },
        {
          piece: "queen",
          player: "black",
        },
        {
          piece: "king",
          player: "black",
        },
        {
          piece: "bishop",
          player: "black",
        },
        {
          piece: "knight",
          player: "black",
        },
        {
          piece: "rook",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "pawn",
          player: "black",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "",
          player: "",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "pawn",
          player: "white",
        },
        {
          piece: "rook",
          player: "white",
        },
        {
          piece: "knight",
          player: "white",
        },
        {
          piece: "bishop",
          player: "white",
        },
        {
          piece: "queen",
          player: "white",
        },
        {
          piece: "king",
          player: "white",
        },
        {
          piece: "bishop",
          player: "white",
        },
        {
          piece: "knight",
          player: "white",
        },
        {
          piece: "rook",
          player: "white",
        },
      ],
    };
  },
  methods: {
    drag(event) {
      event.dataTransfer.setData("text", event.target.id);
    },
    drop(event) {
      let data = event.dataTransfer.getData("text");
      event.target.appendChild(document.getElementById(data));
    },
    oddOrEven(squareId) {
      const [row, col] = coordinates(squareId);
      return row % 2 === col % 2 ? "odd" : "even";
    },
    getPieceImage(square) {
      return square.player === "white" ? whiteImages[square.piece] : blackImages[square.piece];
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
