<template>
  <div class="container">
    
    <!-- Map Start -->
    <b-map class="bm-view" :center="center" :zoom="zoom"></b-map>
    <!-- Map Ended -->
    
      <Row style="background:#eee;padding:20px">
        <Col span="11">
            <Card :bordered="false">
                <p slot="title">无边框卡片</p>
                <p>卡片内容</p>
                <p>卡片内容</p>
                <p>卡片内容</p>
            </Card>
        </Col>
        <Col span="11" offset="2">
            <Card shadow>
                <p slot="title">使用阴影效果的卡片</p>
                <p>卡片内容</p>
                <p>卡片内容</p>
                <p>卡片内容</p>
            </Card>
        </Col>
    </Row>
  </div>
</template>

<script>
import BMap from "./components/BaiduMap.vue";
export default {
  name: "App",
  components: {
    BMap,
  },
  data() {
    return {
      center: {
        lng: 116.404,
        lat: 39.915,
      },
      zoom: 13,
    };
  },
  mounted() {},
  methods: {},
};
</script>

<style lang ="less" scoped>
.container {
  width: 100%;
  height: 100%;
}
/* Map Style Start */
.bm {
  &-view {
    width: 100%;
    height: 600px;
  }
}
/* Map Style Ended */
</style>
