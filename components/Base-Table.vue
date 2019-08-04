<template>
  <div class="table-wrp">
    <table :class='bigTable? "bigCells" : ""'>
      <thead>
        <tr>
          <th v-for='(thCell, thIndex) of head' :key='thIndex'>
            {{ thCell }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for='(row, rowIndex) of rows' :key='rowIndex'>
          <td v-for='(tdCell, tdIndex) of row' :key='tdIndex'>
            {{ tdCell }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data: () => ({
    head: [],
    rows: [],
  }),
  props: {
    content: {},
    bigTable: false,
  },
  mounted() {
    this.fillTable()
  },
  methods: {
    fillTable() {
      this.head =  Object.keys(this.content[0])
      this.rows = this.content
    }
  },
  computed: {
  },
}
</script>

<style scoped>
table, td, th {
  border: 1px solid #07a02d;
}

table {
  border-collapse: collapse;
  min-width: 100%;
}

th {
  padding: 20px 7px;
  text-align: left;
}

tbody>tr:hover {
  background-color: #f8fff4;
}

td {
  padding-left: 7px;
  padding-right: 7px;
}

thead {
  background-color: #e5fbda;
}

.table-wrp {
  margin: 20px 0;
}

.bigCells td {
  padding-top: 20px;
  padding-bottom: 20px;
}
</style>
