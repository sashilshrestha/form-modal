<template>
  <div class="drawer-container">
    <div class="drawer-content">
      <div class="mail-image">
        <img :src="mailImg" alt="" />
      </div>
      <div class="mail-input">
        <h1>Subscribe to moregenland</h1>
        <app-input
          label="E-Mail-Adresse *"
          placeholder="ex. name@email.com"
          type="text"
        ></app-input>
        <button type="submit">Open NewsLetter Modal</button>
        <div class="close-button" @click="$emit('close-modal')">
          <img :src="closeImg" alt="" />
        </div>
      </div>
    </div>
    <div class="overlay" @click="toggleDrawer"></div>
  </div>
</template>

<script>
import mailImg from '../assets/mail.png';
import closeImg from '../assets/close.png';
import AppInput from './AppInput.vue';

export default {
  name: 'AppModal',
  components: { AppInput },
  data() {
    return {
      mailImg,
      closeImg,
    };
  },
};
</script>

<style lang="scss" scoped>
.drawer-container {
  position: fixed;
  top: 0;
  right: 0;
  height: 100%;
  width: 100%;
  .drawer-content {
    background: #d4f0eb;
    position: absolute;
    max-width: 1085px;
    width: 100%;
    height: fit-content;
    right: 50%;
    top: 50%;
    transform: translate(50%, -50%);
    display: flex;
    justify-content: space-between;

    .close {
      cursor: pointer;
      text-decoration: underline;
    }

    .description {
      h2 {
        margin: 0 0 1rem;
      }
      p {
        padding: 0 1rem 0 0rem;
      }
    }

    .mail-image {
      background-color: white;
      display: flex;
      flex: auto;
      flex-direction: column;
      justify-content: center;
      height: 525px;

      img {
        transform: scale(0.85);
      }
    }
    .mail-input {
      padding: 60px;
      max-width: 593px;
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;

      h1 {
        font-family: 'Lato', sans-serif;
        font-size: 36px;
        font-weight: 900;
        margin: 0 0 28px 0;
      }
    }

    .close-button {
      position: absolute;
      top: 1.4rem;
      right: 1.4rem;
      cursor: pointer;
      transition: all 0.1s ease-in-out;

      &:hover {
        transform: scale(1.15);
      }
    }
  }
  .overlay {
    position: absolute;
    background-color: rgba(#dbdbdb, 0.3);
    backdrop-filter: blur(5px);
    width: 100%;
    height: 100%;
    z-index: -1;
  }
}

@media screen and (max-width: 1150px) {
  .drawer-container {
    .drawer-content {
      flex-direction: column;
      max-width: 525px;

      .mail-image {
        height: 300px;
        img {
          height: inherit;
          object-fit: contain;
        }
      }
    }
  }
}
</style>
