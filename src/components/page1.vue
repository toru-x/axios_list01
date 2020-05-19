<template>
<div id="axios_test">
  <div id="axios-ip">
    <div>
      <div>
        <input @click="receiveIp" type="button" value="測定値を取得" />
      </div>
    </div>
  </div>

  <div id="send-ip">
    <div>
      <div>
        <input @click="sendIp" type="button" value="測定値を送信" />
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "ReceiveIp",
  methods: {
    receiveIp() {
      this.axios
//        .post("http://www.tic-keisokuki.com:5000/pure_flow_data_send")
        .post("http://localhost:5000/post_send")
        .then(response => {
          alert(JSON.stringify(response.data));
          console.log(response.data)
})
        .catch(e => {
          alert(e);
        });
    },
    sendIp() {
      this.axios
        .post("http://localhost:5000/post_receive",{
          temp: "10",
          humi: "1120",
          pres: "1010"
        })
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
