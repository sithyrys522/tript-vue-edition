<template>
  <div>
    <table>
      <tr v-for="row in boardState" :key="row">
        <td v-for="i in row" :key="i">
          <cell 
            :val="i"
            class="cell"
            :class="[
              i == 1 || i == 4 || i == 7 ? 'center' : '',
              i == 3 || i == 4 || i == 5 ? 'middle' : ''
            ]"
          ></cell>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import cell from './cell.vue';

export default {
  components: {
    cell
  },
  props: {
    boardState: {
      default: [
      [0, 1, 2],
      [3, 4, 5],
      [6, 7, 8]
      ]
    },
    isXTurn: {
      type: Boolean,
      default: true
    }
  }
};
</script>

<style>
table {
  margin: auto;
  width: 50%;
}

.cell {
  height: 50px;
  width: auto;
  padding: 15px;
}

.middle {
  border-top: solid;
  border-top-color: black;
  border-bottom: solid;
  border-bottom-color: black;
}

.center {
  border-left: solid;
  border-left-color: black;
  border-right: solid;
  border-right-color: black;
}
</style>
