<template>
  <footer class="app-footer">
    <div class="container">
      <div class="app-footer__parent">
        <div class="app-footer__parent-box">
          <h3>About Us</h3>
          <p>About us</p>
          <p>Why us</p>
          <p>Customer Stories</p>
          <p>Press Resources</p>
          <p>Press Releases</p>
        </div>
        <div class="app-footer__parent-box">
         <div>
            <h3>Contact</h3>
            <a href="https://telegram.me/@komisaraleksandr">
            <img class="app-footer__parent-box-icon" src=../assets/telegram.svg alt="telegram">
          </a>
          <a href="https://workspace.google.com/intl/uk/">
            <img class="app-footer__parent-box-icon" src=../assets/g.svg alt="mail">
          </a>
          <a href="https://www.facebook.com/">
            <img class="app-footer__parent-box-icon" src=../assets/fb.svg alt="facebook">
          </a>
         </div>
          <span class="app-footer__logo">Web/-</span>
          <p> &#169; 2021</p>
        </div>
        <div class="app-footer__parent-box">
        <h3>Testimoanials</h3>
        <p>Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industr standard dummy text ever
          since the 1500s</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'AppFooter',
  props: {
    msg: String,
  },
};
</script>

<style scoped>
    .container {
      width: 1200px;
    }

    .app-footer {
      background: #2e2a2c;
      color: blanchedalmond;
    }

    .app-footer__parent {
      display: flex;
      flex-direction: row;
      justify-content: center;
      padding: 20px 0;
    }

    .app-footer__parent-box {
      text-align: center;
      width: 33%;
      margin: 20px;
    }

    .app-footer__parent-box-icon {
      width: 40px;
      padding: 5px;
    }

    @media screen and (max-width: 1180px) {
      .container {
        width: 920px;
      }
    }

    @media screen and (max-width: 920px) {
      .container {
        width: 720px;
      }
    }

    @media screen and (max-width: 720px) {
      .container {
       width: 480px;
      }
    }

  @media screen and (max-width: 480px) {
      .container {
        width: 350px;
      }
  }
</style>
