<template>
  <div class="dashboard">
    <h1>관리자 대시보드</h1>
    <!-- input -->
    <section class="section-1">
      <span><span style="color: red">*</span> 기간</span>
      <input type="date" v-model="targetDate" />
      <span>현장명</span>
      <select name="" id="">
        <option value=""></option>
      </select>
    </section>

    <!-- 알림 -->
    <section class="section-2">
      <h3>알림</h3>
      <table>
        <thead>
          <tr>
            <th>번호</th>
            <th>현장명</th>
            <th>발생 시간</th>
            <th>카메라 번호</th>
            <th>알림 내용</th>
            <th>확인여부</th>
            <th>진행 상황</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(alert, idx) in alertList" :key="idx">
            <td>{{ alert.no }}</td>
            <td>{{ alert.name }}</td>
            <td>{{ alert.time }}</td>
            <td>{{ alert.camNo }}</td>
            <td>{{ alert.alertContent }}</td>
            <td>{{ alert.confirmFlag }}</td>
            <td>{{ alert.progress }}</td>
          </tr>
        </tbody>
      </table>
    </section>

    <!-- 현장이미지, 진행상황 -->
    <section class="section-3">
      <div>
        <img src="../../assets/logo.png" alt="" />
      </div>
      <div>
        <h1>진행 상황</h1>

        <button></button>
        <select name="" id="">
          <option value=""></option>
          <option value=""></option>
          <option value=""></option>
        </select>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      targetDate: new Date(),
      alertList: [
        {
          no: 99030,
          name: "통영에코파워",
          time: "2023.07.20 12:19",
          camNo: "4번",
          alertContent: "사람 쓰러짐 감지",
          confirmFlag: "Y",
          progress: "현장 조치 완료",
        },
      ],
      // targetImg: require('../src/assets/logo.png')
    };
  },
};
</script>

<style scoped>
.dashboard {
  position: absolute;
  width: 100vw;
  height: 100vh;
}
.section-1 {
  /* flex: content; */
  position: relative;
  background: lightgray;
  width: 90%;
  height: 10%;
  left: 50%;
  transform: translateX(-50%);
}
.section-1 span {
  font-size: 1.6em;
}

.section-2 {
  position: relative;
  width: 90%;
  left: 50%;
  transform: translateX(-50%);
}
</style>
