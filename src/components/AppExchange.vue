<template>
  <div class="container">
    <div class="app-exchange">
      <h2 class="app-exchange__title">Exchange</h2>
      <ul v-if="exchange.length"
        class="app-exchange__list">
        <li v-for="(exchange, index) in exchange"
          :key= "index"
          class="app-exchange__item"
        >
          {{exchange.cc}}:{{exchange.rate}} ({{exchange.txt}})
        </li>
      </ul>
      <div v-else>
          No exchange
      </div>
    </div>
  </div>
</template>

<script>
import axiosClient from '@/plugins/axiosClient';

export default {
  name: 'AppExchange',
  data() {
    return {
      exchange: [],
    };
  },
  mounted() {
    this.fetchExchange();
  },
  methods: {
    fetchExchange() {
      axiosClient.get('exchange')
        .then(({ data }) => {
          this.exchange = data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped>
    .app-exchange {
      background: linear-gradient(45deg,
      #fff1eb, #ace0f9);
      background-size: 400% 400%;
      animation: gradient 10s ease infinite;
      border-radius: 20px;
      margin-top: 20px;
      margin-bottom: 20px;
      padding: 20px;
    }

    @keyframes gradient {
      0% {background-position: 0 50%;
      }
      50%  {background-position: 100% 50%;
      }
      100%  {background-position: 0 50%;
      }
    }

    .app-exchange__title {
      text-align: center;
    }

    .app-exchange__list {
      overflow: auto;
      height: 400px;
    }

    .app-exchange__list-item {
      list-style-type: none;
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
