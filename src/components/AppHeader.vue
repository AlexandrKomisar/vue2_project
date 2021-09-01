<template>
  <header class="app-header">
    <div class="container">
      <span class="app-header__logo">Web/-</span>
      <div class="app-header__nav">
        <a href="#" class="app-header__nav-item">Solution</a>
        <a href="#" class="app-header__nav-item">Products</a>
        <a href="https://github.com/AlexandrKomisar?tab=repositories" class="app-header__nav-item">Portfolio</a>
        <a href="#" class="app-header__nav-item">Contact</a>
      </div>
      <div class="app-header__cofee">
        <img src="../assets/icon.png" alt="cofee">
      </div>
       <div class="app-header__clock">
         <div class="clock" v-if="hourtime != ''">
          <div class="clock__hours">
            <span class="clock__hourtime" v-text="hourtime"></span>
            <span v-text="hours"></span>
          </div>
    <div class="clock__minutes" v-text="minutes"></div>
    <div class="clock__seconds" v-text="seconds"></div>
  </div>
      </div>
    </div>
  </header>
</template>

<script>
import {
  SECOND, HOUR, getHourTime, getZeroPad,
} from '@/plugins/filters';

export default {
  name: 'AppHeader',
  data() {
    return {
      hours: 0,
      minutes: 0,
      seconds: 0,
      hourtime: '',
    };
  },
  mounted() {
    const timer = window.setTimeout(this.updateDateTime, SECOND);
    this.$on('hook:destroyed', () => window.clearTimeout(timer));
  },
  methods: {
    updateDateTime() {
      const now = new Date();
      this.hours = now.getHours();
      this.minutes = getZeroPad(now.getMinutes());
      this.seconds = getZeroPad(now.getSeconds());
      this.hourtime = getHourTime(this.hours);
      this.hours = this.hours % HOUR || HOUR;
      this.$options.timer = window.setTimeout(this.updateDateTime, SECOND);
    },
  },
};
</script>

<style>

.container {
  width: 1200px;
  margin: 0 auto;
}

.app-header {
  background-image: url('../assets/bg.png');
  background-position: center, center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 500px;
  padding: 50px;
  color: white;
  position: relative;
}

.app-header__logo {
  font-size: 50px;
}

.app-header__nav {
  display: flex;
  justify-content: space-around;
}

.app-header__nav-item{
  text-decoration: none;
  color: #ffffff;
  padding: 20px;
  font-size: 25px;
}

.app-header__nav-item:hover {
  color: #a1bbd4;
}

.app-header__cofee {
  position: absolute;
  top: 220px;
}

.app-header__clock {
  position: absolute;
  top: 300px;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
}

.clock {
  background: #fff;
  border: 0.3rem solid #fff;
  border-radius: 0.5rem;
  display: inline-block;
  margin-bottom: 1em;
}
.clock__hours,
.clock__minutes,
.clock__seconds {
  background: linear-gradient(to bottom, #26303b 50%, #2c3540 50%);
  display: inline-block;
  color: #fff;
  font-family: 'Nunito', sans-serif;
  font-size: 3rem;
  font-weight: 300;
  padding: 0.5rem 1rem;
  text-align: center;
  position: relative;
}
.clock__hours {
  border-right: 0.15rem solid #fff;
  border-radius: 0.5rem 0 0 0.5rem;
}
.clock__minutes {
  border-right: 0.15rem solid #fff;
}
.clock__seconds {
  border-radius: 0 0.5rem 0.5rem 0;
}
.clock__hourtime {
  font-size: 1rem;
  position: absolute;
  top: 2px;
  left: 8px;
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
  .app-header__nav {
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-end;
  }
}

@media screen and (max-width: 720px) {
    .container {
    width: 480px;
  }
  .app-header__clock {
    top: 170px;
    left: 200px;
  }
}

@media screen and (max-width: 480px) {
    .container {
    width: 350px;
  }
  .app-header__clock {
   top: 450px;
  }

  .app-header__cofee {
    display: none;
  }
   .app-header__nav {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}

</style>
