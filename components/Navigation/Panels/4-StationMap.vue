<template>
  <div class="wrapper">
    <Panel>
      <div class="justify-content-space-between align-items-flex-end">
        <span class="font-size-huge color-focus"> 車站內部路線 </span>
      </div>

      <div
        v-for="(station, index) in data.sationMaps"
        :key="index"
        class="station"
      >
        <span class="font-size-mini color-secondary">
          {{ station.type }}
        </span>
        <span class="font-size-regular color-text">
          {{ station.station }}
        </span>
        <img :src="station.image" />
        <hr />
      </div>

      <div class="cols mt-4">
        <div class="col-6 p-1">
          <Button
            @click="$emit('next', 'setNotice')"
            color="#e9a668"
            size="small"
          >
            <span class="mdi mdi-bell-ring"></span>
            設定下車提醒
          </Button>
        </div>

        <div class="col-6 p-1">
          <Button @click="$emit('next', 'getDetail')" size="small"
            >詳細路線資料</Button
          >
        </div>
      </div>
    </Panel>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
    },
  },
  mounted() {
    this.$set(this.data, 'sationMaps', [
      {
        type: '起點',
        station: '東門站',
        image: 'https://web.metro.taipei/img/ALL/stationprofile/134.jpg',
      },
      {
        type: '轉乘站',
        station: '大安站',
        image: 'https://web.metro.taipei/img/ALL/stationprofile/134.jpg',
      },
    ])
  },
}
</script>

<style scoped>
.wrapper {
  width: 100%;
  box-sizing: border-box;
}

.wrapper > div {
  margin-top: 1rem;
}

.station {
  margin-top: 1rem;
  display: flex;
  flex-direction: column;
}

.station > hr {
  width: 100%;
}

.station > * {
  margin-top: 0.4rem;
}
</style>
