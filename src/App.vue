<template>
  <div id="grid">
    <div v-for="squareId in 64" :key="squareId">
      <div
        class="square"
        :class="oddOrEven(squareId)"
        @drop.prevent="drop($event, squareId - 1)"
        @dragover.prevent
      >
        <img
          v-if="chessBoard[squareId - 1].piece !== ''"
          :id="squareId"
          :src="getPieceImage(chessBoard[squareId - 1])"
          width="50"
          height="50"
          :data-piece="chessBoard[squareId - 1].piece"
          :data-player="chessBoard[squareId - 1].player"
          draggable="true"
          @dragstart="drag($event, squareId - 1)"
        />
      </div>
    </div>
  </div>
</template>

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
    drag(event, squareId) {
      // event.dataTransfer.setData("piece", event.target.dataset.piece);
      // event.dataTransfer.setData("player", event.target.dataset.player);
      event.dataTransfer.setData("squareId", squareId);
    },
    canPieceMove(sourceSquareId, targetSquareId) {
      const targetPiece = this.chessBoard[targetSquareId].piece;
      const targetPlayer = this.chessBoard[targetSquareId].player;
      const [targetRow, targetCol] = coordinates(targetSquareId);
      const sourcePiece = this.chessBoard[sourceSquareId].piece;
      const sourcePlayer = this.chessBoard[sourceSquareId].player;
      const [sourceRow, sourceCol] = coordinates(sourceSquareId);

      if (targetPlayer === sourcePlayer) {
        console.warn("Two pieces of the same player");
        return false;
      }
      // for white pawns
      if (sourcePlayer === "white") {
        if (targetCol === sourceCol) {
          if (sourceRow === 7 && targetRow === 5) {
            return true;
          }
          if (targetRow === sourceRow - 1) {
            return true;
          }
          console.warn("Pawns can't go so far ahead.");
        } else {
          console.warn("Pawns must move forward");
        }
      }

      // for black pawns
      if (sourcePlayer === "black") {
        if (targetCol === sourceCol) {
          if (sourceRow === 2 && targetRow === 4) {
            return true;
          }
          if (targetRow === sourceRow + 1) {
            return true;
          }
          console.warn("Pawns can't go so far ahead.");
        } else {
          console.warn("Pawns must move forward");
        }
      }
      return false;
    },
    drop(event, targetSquareId) {
      const sourceSquareId = +event.dataTransfer.getData("squareId");
      const targetPiece = this.chessBoard[targetSquareId].piece;
      const targetPlayer = this.chessBoard[targetSquareId].player;
      const [targetRow, targetCol] = coordinates(targetSquareId);
      const sourcePiece = this.chessBoard[sourceSquareId].piece;
      const sourcePlayer = this.chessBoard[sourceSquareId].player;
      const [sourceRow, sourceCol] = coordinates(sourceSquareId);

      if (this.canPieceMove(sourceSquareId, targetSquareId)) {
        this.chessBoard[targetSquareId].piece = sourcePiece;
        this.chessBoard[targetSquareId].player = sourcePlayer;
        this.chessBoard[sourceSquareId].piece = "";
        this.chessBoard[sourceSquareId].player = "";
      }
    },
    oddOrEven(squareId) {
      const [row, col] = coordinates(squareId);
      return row % 2 === col % 2 ? "odd" : "even";
    },
    getPieceImage(square) {
      return square.player === "white"
        ? whiteImages[square.piece]
        : blackImages[square.piece];
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
