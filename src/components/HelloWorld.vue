<template>
  <div>
    <h3 class="sub-title">Authentication Number list</h3>

    <div class="text-align-center" v-if="selectedDan">DAN-{{ selectedDan }}</div>
    <div class="text-align-center" v-if="selectedDacn">DACN-{{ selectedDacn }}</div>
    <table id="table">
      <tr>
        <th>Phone Number</th>
        <th>DAN</th>
        <th>DACN</th>
        <th></th>
      </tr>
      <tr v-for="(item, index) of lists" :key="index">
        <td>{{ item.id }}</td>
        <td><input type="radio" name="dan" :value="item.id" v-model="selectedDan" /></td>
        <td><input type="radio" name="dacn" :value="item.id" v-model="selectedDacn" /></td>
        <td><input type="checkbox" :disabled="item.id === selectedDan || item.id === selectedDacn"/></td>
      </tr>
    </table>
    <button @click="addMore" class="add-more-btn">Add Number</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      selectedDacn: '',
      selectedDan: '',
      lists: [
        {
          id: 8320568938,
          dan: '',
          dacn: '',
          checked: ''
        },
        {
          id: 7359564121,
          dan: '',
          dacn: '',
          checked: ''
        },
        {
          id: 9428703967,
          dan: '',
          dacn: '',
          checked: ''
        }
      ]
    }
  },
  methods: {
    addMore() {
      this.lists.push({
          id: Math.floor(Math.random() * 9000000000) + 1000000000,
          dan: '',
          dacn: '',
          checked: ''
        })
    }
  }
}
</script>
<style scoped>
#table {
  border-collapse: collapse;
  text-align: center;
  justify-content: center;
  width: 100%;
}
#table th {
  border-bottom: 1.1px solid #1b0909;
}
#table td, #table th {
  padding: 8px;
  text-align: left;

}
#table tr:nth-child(even){background-color: #f2f2f2;}
/* #table tr:hover {background-color: #ddd;} */
#table th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  color: black;
}
.add-more-btn {
  text-align: start;
  background-color: transparent;
  color: #0160AC;
  border: none;
  cursor: pointer;
  margin-top: 10px;
  font-size: 16px;
}
.sub-title {
  margin-left: 7px;
}

input[type=radio]{
  width: 25px;
  height: 25px;
  text-align: start;
}

input[type=checkbox] {
  margin: 4px 0 0;
  line-height: normal;
  width: 25px;
  height: 25px;
}
.text-align-center {
  text-align: center;
}

</style>
