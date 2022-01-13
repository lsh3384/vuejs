<template>
  <div>
    
    <h1>Welcome to {{title1}}!</h1>
    
    <input type="text" v-model="input1" />
    
    <button type="button" @click="getData">Get</button>

    <button type="button" @click="setData">Set</button>

    <select class="form-control" v-model="region" @change="changeRegion">
      <option :key="i" :value="d.v" v-for="(d,i) in options">{{d.t}}</option>
    </select>

    <table class="table table-bordered" v-if="tableShow">
      <tr :key="i" v-for="(d,i) in options">
        <td>{{d.v}}</td>
        <td>{{d.t}}</td>
      </tr>
    </table>

    <table class="table table-bordered" v-if="tableShow">
      <tr :key="name" v-for="(value, name) in sensor_data">
        <td>{{name}}</td>
        <td>{{value}}</td>
      </tr>
    </table>

    <button type="button" @click='getPropData'>Get_Prop_Data</button>

  </div>
</template>
<script>
export default {
  // props: ['sensor_data'],
  
  props: {
    sensor_data: Object,
  },
  data() {
    return {
      title: "개발 테스트 페이지",
      title1: "Seoul",
      input1: "abcdefg",
      options: [
        {v:"S", t:"Seoul"},
        {v:"J", t:"Jeju"},
        {v:"B", t:"Busan"},
      ],
      region: "B",
      tableShow: true,
    }
  },
  watch: {
    input1() {
      console.log(this.input1);
    }
  },
  methods: {
    getData() {
      alert(this.input1);
    },
    setData() {
      this.input1 = "12345";
    },
    changeRegion(){
      alert(this.region);
    },
    getPropData() {
      console.log('temp: ', this.sensor_data.temp);
      console.log('humi: ', this.sensor_data.humi);
    }
  },

  // beforeCreate() {
  //   console.log("beforeCreate");
  // },
  // created() {
  //   console.log("created");
  //   alert(this.input1);
  // },
  // beforeMount() {
  //   console.log("beforeMount");
  // },
  // mounted() {
  //   console.log("mounted");
  // },
  // beforeUpdate() {
  //   console.log("beforeUpdate");
  // },
  // updated() {
  //   console.log("updated");
  // },
  // beforeDestroy() {
  //   console.log("beforeDestroy");
  // },
  // destroyed() {
  //   console.log("destroyed");
  // }
}
</script>