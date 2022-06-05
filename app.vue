<template>
  <div class="check-global">
    <h1>Jeu de dames</h1>
    <div class="check-checkerboard">
      <div class="check-line" v-for="y in 10" :key="y">
        <template v-if="y % 2 === 0">
          <div
            v-for="index in 10"
            :key="index"
            :style="
              index % 2 === 0
                ? 'background-color: #D2691E '
                : 'background-color: #8B4513 '
            "
            class="check-case"
          >
            <Pion
              v-if="isPieceInCase(index, y)"
              :color="isPieceInCase(index, y).colorPiece"
            />
          </div>
        </template>
        <template v-if="y % 2 !== 0">
          <div
            v-for="index in 10"
            :key="index"
            :style="
              index % 2 !== 0
                ? 'background-color: #D2691E '
                : 'background-color: #8B4513 '
            "
            class="check-case"
          >
            <Pion
              v-if="isPieceInCase(index, y)"
              :color="isPieceInCase(index, y).colorPiece"
            />
          </div>
        </template>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
class ArrayWithPiece {
  case: number;
  colorPiece: string;
}
export default {
  data() {
    return {
      caseWithPiece: [
        {
          case: 2,
          colorPiece: "black",
        },
        {
          case: 4,
          colorPiece: "black",
        },
        {
          case: 6,
          colorPiece: "black",
        },
        {
          case: 8,
          colorPiece: "black",
        },
        {
          case: 10,
          colorPiece: "black",
        },
        {
          case: 11,
          colorPiece: "black",
        },
        {
          case: 13,
          colorPiece: "black",
        },
        {
          case: 15,
          colorPiece: "black",
        },
        {
          case: 17,
          colorPiece: "black",
        },
        {
          case: 19,
          colorPiece: "black",
        },
        {
          case: 22,
          colorPiece: "black",
        },
        {
          case: 24,
          colorPiece: "black",
        },
        {
          case: 26,
          colorPiece: "black",
        },
        {
          case: 28,
          colorPiece: "black",
        },
        {
          case: 30,
          colorPiece: "black",
        },
        {
          case: 31,
          colorPiece: "black",
        },
        {
          case: 33,
          colorPiece: "black",
        },
        {
          case: 35,
          colorPiece: "black",
        },
        {
          case: 37,
          colorPiece: "black",
        },
        {
          case: 39,
          colorPiece: "black",
        },
        {
          case: 62,
          colorPiece: "white",
        },
        {
          case: 64,
          colorPiece: "white",
        },
        {
          case: 66,
          colorPiece: "white",
        },
        {
          case: 68,
          colorPiece: "white",
        },
        {
          case: 70,
          colorPiece: "white",
        },
        {
          case: 71,
          colorPiece: "white",
        },
        {
          case: 73,
          colorPiece: "white",
        },
        {
          case: 75,
          colorPiece: "white",
        },
        {
          case: 77,
          colorPiece: "white",
        },
        {
          case: 79,
          colorPiece: "white",
        },
        {
          case: 82,
          colorPiece: "white",
        },
        {
          case: 84,
          colorPiece: "white",
        },
        {
          case: 86,
          colorPiece: "white",
        },
        {
          case: 88,
          colorPiece: "white",
        },
        {
          case: 90,
          colorPiece: "white",
        },
        {
          case: 91,
          colorPiece: "white",
        },
        {
          case: 93,
          colorPiece: "white",
        },
        {
          case: 95,
          colorPiece: "white",
        },
        {
          case: 97,
          colorPiece: "white",
        },
        {
          case: 99,
          colorPiece: "white",
        },
      ],
    };
  },
  methods: {
    isPieceInCase(x: number, y: number) {
      const value = (x - 1) * 10 + y;
      const range = this.caseWithPiece.find((c: ArrayWithPiece) => c.case === value);

      if (range) {
        return range;
      }
      return null;
    },
  },
};
</script>
<style scoped>
.check-global {
  text-align: center;
}

.check-checkerboard {
  width: 800px;
  height: 800px;
  margin: 20px auto;
  border: 8px #a0522d double;
  display: flex;
}

.check-case {
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.check-line {
  height: 80px;
}
</style>
