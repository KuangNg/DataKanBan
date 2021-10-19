<template>
  <baidu-map
    id="mapContent"
    class="map"
    ak="H6EfbaNfADmMYNwp5cK9Og3Lsj13PWew"
    :center="center"
    :zoom="zoom"
    @ready="mapReady"
  >
    <bm-marker :position="{ lng: 116.404, lat: 39.915 }" :dragging="true">
    </bm-marker>
  </baidu-map>
</template>
<script>
import BaiduMap from "vue-baidu-map/components/map/Map.vue";
import BmMarker from "vue-baidu-map/components/overlays/Marker.vue";//导入地图标志点
export default {
  name: "BMap",
  props: {
    /**
     * 密钥
     */
    ak: {
      type: String,
      require: true,
    },
    /**
     * 中心点
     */
    center: {
      type: Object,
      default: () => {},
    },
    /**
     * 缩放
     */
    zoom: {
      type: Number,
      defualt: 15,
    },
    /**
     * 覆盖点数据
     */
    markerData: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {

    };
  },
  components: {
    BaiduMap,
    BmMarker,
  },

  methods: {
    /**
     * 地图画后设置地图默认的信息
     * @method 地图已加载
     * @param BMap：百度地址构件函数
     * @param map：当前百度地图实例
     * @param mapv：mapv构造函数
     */
    mapReady({ BMap, map }) {
      console.log("地图初始准备", BMap, map);
    },
  },
};
</script>

<style lang="less" scoped>
    .map{
        width: 100%;
        height: 100%;
    }
</style>