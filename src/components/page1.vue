<template>
  <div id="search-ip">
    <div>
      <div>
        <input @click="getIp" type="button" value="IPを取得" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchIp",
  methods: {
    getIp() {
      this.axios
//        .post("http://www.tic-keisokuki.com:5000/pure_flow_data_send")
//        .post("http://www.tic-keisokuki.com:5000/thermograph_data_send")
        .post("http://www.tic-keisokuki.com:5000/thp_data_send")
        .then(response => {
          alert(JSON.stringify(response.data));
          console.log(response.data)
})
        .catch(e => {
          alert(e);
        });
    }
  }
};
</script>
