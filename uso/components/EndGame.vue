<template>
  <!-- transfer over to components -->

  <div>
    <div class="endgame__page">
      <div class="endgame__page--container">
        <div class="endgame__header">
          <div class="header__left">
            <div id="leftSide">
              <div id="leftTitle">
                {{
                  beatmapData.metadata.TitleUnicode +
                  ' ' +
                  beatmapData.metadata.Version
                }}
              </div>
              <div id="leftTitle">
                beatmap by {{ beatmapData.metadata.Creator }}
              </div>
              <h3></h3>
            </div>
          </div>

          <div class="header__right">
            <div id="rightSide">RANKING</div>
          </div>
        </div>

        <div class="endgame__stats--container">
          <div class="stats__flow">
            <h1 class="title">Results</h1>
            <div class="content-sidebar">
              <div id="left__col" class="col">

                <div class="score__container">
                  <div class="score">Score: {{ Math.floor(stats.score) }} |</div>
                  <div class="score">Combo: {{ stats.maxCombo }} |</div>
                  <div class="score">
                    Accuracy: {{ Math.round(stats.accuracy * 10000) / 100 }}%
                  </div>
                </div>

                <div class="stats__results">
                  <div class="scoreValues">
                    <div id="s320" class="stats">300</div>
                    <div id="s300" class="stats">300</div>
                    <div id="s200" class="stats">200</div>
                  </div>   
                  <div class="scoreValues">
                    <div class="stats">x{{ totalHits['320'] }}</div>
                    <div class="stats">x{{ totalHits['300'] }}</div>
                    <div class="stats">x{{ totalHits['200'] }}</div>
                  </div>
                  <div class="scoreValues">
                    <div id="s100" class="stats">100</div>
                    <div id="s50" class="stats">50</div>
                    <div id="s0" class="stats">miss!</div>
                  </div>
                  <div class="scoreValues">
                    <div class="stats">x{{ totalHits['100'] }}</div>
                    <div class="stats">x{{ totalHits['50'] }}</div>
                    <div class="stats">x{{ totalHits['0'] }}</div>
                  </div>
                </div>
              </div>
              <div id="right__col" class="col">
                <div class="letterRanking">{{ grade }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <nuxt-link to="/beatmaps" class="beatmap__btnClass">
        <div id="beatmap__btnId">back</div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    beatmapData: {
      required: true,
      type: Object,
    },
    totalHits: {
      required: true,
      type: Object,
    },
    stats: {
      required: true,
      type: Object,
    },
  },
  data() {
    return {
      grade: null,
    };
  },
  created() {
    const t = this;

    if (t.stats.accuracy === 1) t.grade = 'SS';
    else if (t.stats.accuracy > 0.95) t.grade = 'S';
    else if (t.stats.accuracy > 0.9) t.grade = 'A';
    else if (t.stats.accuracy > 0.8) t.grade = 'B';
    else if (t.stats.accuracy > 0.7) t.grade = 'C';
    else t.grade = 'D';
  },
};
</script>

<style scoped>
/* declarations */

#leftSide {
  font-weight: 300;
  text-shadow: 4px 2px 3px #000;
}

#leftTitle {
  font-size: 4rem;
  text-shadow: 4px 2px 3px #000;
}

#rightSide {
  font-size: 12.5rem;
  font-weight: 500;
  padding: 0 15rem 0 0;
  text-shadow: 4px 2px 3px #000;
}

#statsLeft {
  font-size: 6rem;
}

.title {
  font-size: 10.5rem;
  font-weight: 400;
  text-shadow: 4px 2px 3px #000;
}

.score__container {
  display: flex;
  justify-content: center;
}

/* endgame things */

.endgame__page--container {
  display: flex;
  flex-direction: column;
  /* align-items: center; */
  height: 100vh;
  background-image: linear-gradient(
      rgba(30, 30, 30, 0.5),
      rgba(30, 30, 30, 0.5)
    ),
    url('~/assets/images/backgrounds/inazumaEndPg.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
}

.endgame__header {
  padding: 5px 30px 5px 30px;
  opacity: 0.85;

  background: #292a2b;
  color: white;

  display: flex;
  justify-content: space-around;
  align-items: center;
}

.header__left {
  margin-right: auto;
}

.header__right {
  margin-left: auto;
}

.endgame__stats--container {
  padding: 25px;
}

/* o k */

.content-sidebar {
  display: flex;
  flex-wrap: wrap;
  height: 50vh;
}

.content-sidebar > *:nth-child(1) {
  flex: 1 1 65%;
  background: #373738;
  opacity: 0.8;
  height: 47vh;
}

.content-sidebar > *:nth-child(2) {
  flex: 1 1 35%;
  /* background: #373738;
  opacity: 0.8; */
}

#left__col {
  padding: 2rem;
}

.stats__results {
  display: flex;
  align-items: center;
  justify-content: center;
  /* flex-direction: column; */
  flex-wrap: wrap;
  padding: 4.5rem 14.5rem 4.5rem 18.5rem;
  text-shadow: 4px 2px 3px #000;
}

.stats__results > *:nth-child(1) {
  flex: 1 1 25%;
}

.stats__results > *:nth-child(2) {
  flex: 1 1 25%;
}

.stats__results > *:nth-child(3) {
  flex: 1 1 25%;
}

.stats__results > *:nth-child(4) {
  flex: 1 1 15%;
}

.score {
  font-size: 7.5rem;
  font-weight: 500;
  padding: 0 0rem 0 1rem;
  text-shadow: 4px 2px 3px #000;
}

.stats {
  font-size: 7rem;
  height: 7.5rem;
}

#right__col {
  padding: 2.5rem;
  height: 0;
}

.letterRanking {
  text-align: center;
  font-size: 52rem;
  font-weight: 500;
  margin-top: 24rem;
  line-height: 0;
  text-shadow: 4px 2px 3px #000;
}

/* triangle */

.beatmap__btnClass {
  position: fixed;
  cursor: url('~/assets/images/cursor/paimonCursor4.png'), auto;
  left: -0.1rem;
  bottom: -0.1rem;
  width: 20rem;
  height: 20rem;
  /* background-color: #2489c4; */
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  color: #fff;
  /* box-shadow: 0 0.1rem 0.6rem rgb(0 0 0 / 20%); */
  border-radius: 0.3rem;
  background: linear-gradient(
    to bottom left,
    transparent 0%,
    transparent 50%,
    #131313 50%,
    #131313 100%
  );
  /* display: inline-block; */
}

.beatmap__btnClass:hover {
  background: linear-gradient(
    to bottom left,
    transparent 0%,
    transparent 50%,
    #181818 50%,
    #181818 100%
  );
}

#beatmap__btnId {
  font-size: 8.5rem;
  transform: translate(-30px, 60px);
}

/* colors */

#s320 {
  /* background: linear-gradient(to top, red 32%, orange, yellow, green, blue, indigo 75%);
  background-clip: 'text';
  -webkit-background-clip: 'text';
  -webkit-text-fill-color: 'transparent'; */
  color: rgb(74, 255, 228);
}

#s300 {
  color: #fcff64;
}

#s200 {
  color: rgb(111, 255, 111);
}

#s100 {
  color: rgb(85, 73, 255);
}

#s50 {
  color: rgb(97, 97, 97);
}

#s0 {
  color: rgb(224, 46, 46);
}

</style>
