<template>
  <div>
    <div class="under-nav"></div>

    <div id="profile-body">
      <div class="profile-container">
        <div class="cover-photo"></div>

        <div class="profile-details">
          <div class="profile-picture-div">
          <img 
          :src="user[0].image"
            class="profile-picture"
            @click="toggleShowModal()"
          /> 
          <p class="change-pfp-text">CHANGE</p>
         
          </div>
      
            <!-- <h1 class="profile-title">{{user[0].username}}</h1> -->
            <h1 class="profile-title">{{ username }}</h1>
            <h1 id="user__edit" class="profile-title">🖉</h1>
     
        </div>
        <div class="profile-description">
       <p class="description-text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Assumenda, adipisci libero est exercitationem porro harum quasi quisquam, sit modi esse cumque quas consectetur necessitatibus. Praesentium repudiandae aliquid pariatur. Vitae, at!</p>

  <change-pfp  :show-modal='showModal' :all-owned="user[0].characters" />
     </div>
  <section class="collection-section">
     <h1 id="collection-header">Collection</h1>
    <owned-character :all-owned="user[0].characters" />
  </section>
      </div>
    </div>
  </div>
  <!-- copy osu css layout for pfp and header -->
</template>

<script>
import ChangePfp from '../components/ChangePfp.vue';
import ownedCharacter from '../components/OwnedCharacter.vue';
import user from '~/static/user.json';
import characters from '~/static/characters.json';



export default {
  components: {
    ownedCharacter,
    ChangePfp,

  },
  data() {
    return {
      username: this.$auth.user.nickname,
      user,
      characters,
      showModal: false
    };
  },
  methods: {
    toggleShowModal () {
      this.showModal = !this.showModal;
      
    }
  }
  /* created() {
    console.log(user);
  }, */
};
</script>

<style lang="css" scoped>

#profile-body {
  --container-width: 55vw;
  --pfp-size: 120px;
  --pfp-radius: 40px;
  /* width: 100%; */
}

.profile-container {
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
      url('~/assets/images/backgrounds/liyueEndPg.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
}

.cover-photo {
  width: var(--container-width);
  height: 32rem;
  margin-top: 4rem;
  background-image: linear-gradient(
      rgba(62, 54, 104, 0.7),
      rgba(62, 54, 104, 0.7)
    ),
    url('~/assets/images/backgrounds/yaeMiko.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center 25%;
}

.profile-details {
  width: var(--container-width);
  background-image: linear-gradient(rgba(13, 4, 66, 0.7), rgba(13, 4, 66, 0.7)),
    url('~/assets/images/backgrounds/fleeting-colors.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;

  display: flex;
    align-items: center;
    padding: 0 5rem 0 5rem;
}

.profile-picture-div {
  position: relative;
}

.profile-picture {
  width: var(--pfp-size);
  height: var(--pfp-size);
  border-radius: var(--pfp-radius);
  overflow: hidden;
  align-self: flex-end;
  transition: all 300ms ease-in-out;

  margin: -4rem 2.4rem 1.5rem 0;cursor: url('~/assets/images/cursor/paimonCursor4.png'), auto;
  cursor: url('~/assets/images/cursor/paimonCursor4.png'), auto;
}

.profile-picture:hover {
  background: black;
  transform: scale(1.04);
  opacity: 0.85;
}

.profile-picture:hover + .change-pfp-text {
  display: block;
}

.change-pfp-text {
  display: none;
  text-shadow: 0px 3px 2px #000;
  position: absolute;
  top: -29%;
  left: 19%;
  pointer-events: none;
  transition: all 300ms ease-in-out;
        /* top: 16%; */
        /* left: 20%; */
}

.profile-title {
  font-size: 6rem;
    /* line-height: 7rem; */
    font-weight: 400;
}

.profile-description {
  width: var(--container-width);
  padding: 2.5rem 6rem;
  background-image: linear-gradient(rgba(13, 4, 66, 0.466), rgba(13, 4, 66, 0.432)),
    url('~/assets/images/backgrounds/fleeting-colors.jpg');
}

.collection-section {
  width: var(--container-width);
/*  
  background: rgba(0, 0, 255, 0.329); */
  background-image: linear-gradient(rgba(13, 4, 66, 0.7), rgba(13, 4, 66, 0.7)),
    url('~/assets/images/backgrounds/fleeting-colors.jpg');
    background-attachment: fixed;
    padding: 1rem 0;
  margin-bottom: 4rem;

  display: flex;
  flex-direction: row ;
  flex-wrap: wrap;
}

#collection-header {
align-self: center;
    font-size: 5rem;
    font-weight: 500;
    text-transform: uppercase;
    margin: auto;
}

#user__edit {
  margin-left: 2.5rem;
  font-size: 2.5rem;
  cursor: url('~/assets/images/cursor/paimonCursor4.png'), auto;
}

/*
.profile-titlebox {
  width: 55vw;

  background-color: rgb(8, 36, 83);
}
.profile-title {
  display: flex;
  align-items: center;
  font-size: 3.5rem;
  font-weight: 400;
  color: #f6f6f6;
  height: 5.5rem;
  margin: 0.5rem 1rem 0.5rem 3.5rem;
  padding-top: 0.5rem;
}
.profile-details {
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
  /* background-position: center center;
} */
</style>
