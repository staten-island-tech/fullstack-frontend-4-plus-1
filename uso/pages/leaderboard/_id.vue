<template>
  <div>
    <nav-bar />
     <div class="under-nav"></div>
    <div id="lb__index">
      <div class="lb__container">
        <div class="lb__titlebox">
          <h1 class="lb__title">Song id: {{ id }}</h1>
        </div>

        <div class="yae__filler"></div>

        <div class="lb__rankingStats">
          <table class="lb__rankingTable">
            <thead>
              <tr>
                <th class="lb__rankingHeading"></th>
                <th class="lb__rankingHeading lb__rankingHeading--main"></th>
                <th class="lb__rankingHeading">Accuracy</th>
                <th class="lb__rankingHeading">Score</th>
                <th class="lb__rankingHeading lb__rankingHeading--focused">
                  Grade
                </th>
              </tr>
            </thead>

            <tbody>
              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #1
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">Wiichen</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  100%
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  160,000
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                >
                  SS
                </td>

              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #2
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">Sliger</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  98.40%
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  129,750
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                >
                  S
                </td>

              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #3
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">Harshey</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  92.7%
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  68,950
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                >
                  A
                </td>

              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #4
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">Edan</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  87.3%
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  44,500
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                >
                  B
                </td>

              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #5
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">Kenneru</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  74.8%
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                >
                  24,000
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                >
                  C
                </td>

              <!-- delete tables below, just wanted to see how it looks -->

              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #6
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">L Bozo</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
              </tr>
              <tr class="lb__rankingTable__row">
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--rank"
                >
                  #7
                </td>
                <td class="lb__rankingTable__column">
                  <div class="lb__user">L Bozo</div>
                </td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--focused"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
                <td
                  class="lb__rankingTable__column lb__rankingTable__column--dimmed"
                ></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from '../../components/NavBar.vue';

export default {
  components: { NavBar },
  computed: {
    id() {
      return this.$route.params.id;
    },
  },
};
</script>

<style>
.under-nav {
  height: 9.5rem;
}

.lb__index {
  width: 100vw;
}

.lb__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 90.2vh;
  height: 100%;
  background-image: linear-gradient(
      rgba(13, 4, 66, 0.7),
      rgba(16, 51, 112, 0.8)
    ),
    /* url('~/assets/images/backgrounds/fleeting-colors.jpg'); */
      url('~/assets/images/backgrounds/chnBg.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
}

.lb__titlebox {
  width: 55vw;
  margin-top: 2rem;
  background-color: rgb(8, 36, 83);
}

.lb__title {
  display: flex;
  align-items: center;
  font-size: 3.5rem;
  font-weight: 400;
  color: #f6f6f6;
  height: 5.5rem;
  margin: 0.5rem 1rem 0.5rem 3.5rem;
  padding-top: 0.5rem;
}

.yae__filler {
  width: 55vw;
  height: 15vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2.5rem;
  background-image: linear-gradient(
      rgba(62, 54, 104, 0.7),
      rgba(62, 54, 104, 0.7)
    ),
    url('~/assets/images/backgrounds/yaeMiko.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center 25%;
}

/* Leaderboard */

table {
  background-color: transparent;
}

thead {
  display: table-header-group;
  vertical-align: middle;
  border-color: inherit;
}

tr {
  display: table-row;
  vertical-align: inherit;
  border-color: inherit;
}

tbody {
  display: table-row-group;
  vertical-align: middle;
  border-color: inherit;
}

.lb__rankingStats {
  color: #fff;
  font-size: 15rem;
  overflow-x: auto;
  --content-width: 55vw;
  --beatmap-set-container-width: 45vw;
  --sidebar: 25rem;
  width: var(--content-width);
  display: flex;
  align-items: flex-start;
  padding: 1.25rem 2.5rem 2.5rem 2.5rem;
  background-image: linear-gradient(rgba(13, 4, 66, 0.7), rgba(13, 4, 66, 0.7)),
    url('~/assets/images/backgrounds/fleeting-colors.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  margin-bottom: 1rem;
  /* background-position: center center; */
}

.lb__rankingTable {
  transform: translateZ(0);
  width: 100%;
  min-width: 650px;
  white-space: nowrap;
  text-align: center;
  border-spacing: 0 3px;
  border-collapse: separate;
}

.lb__rankingHeading {
  font-weight: 300;
  color: #9599c9;
  padding: 5px 10px;
  text-align: center;
  font-size: 2.25rem;
}

.lb__rankingHeading--main {
  width: 100%;
}

.lb__rankingHeading--focused {
  color: #fff;
}

.lb__rankingHeading--grade {
  padding: 5px 20px;
}

.lb__rankingTable__row {
  background: #161a3d;
  border-radius: 4px;
  font-size: 3.25rem;
}

.lb__rankingTable__column {
  padding: 6px 0;
}

.lb__rankingTable__column:first-child {
  border-top-left-radius: 4px;
  border-bottom-left-radius: 4px;
}

.lb__rankingTable__column--rank {
  text-align: center;
  padding: 0 10px;
  opacity: 1;
}

.lb__rankingTable__column--dimmed {
  color: #9599c9;
}

.lb__user {
  margin-left: 2.25rem;
  display: flex;
  align-items: center;
  font-size: 2.25rem;
  color: #dae0ff;
}
</style>

