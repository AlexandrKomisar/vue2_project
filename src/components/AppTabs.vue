<template>
    <div class="container">
        <div class="app-tabs">
            <button class="app-tabs__item" @click="selectTab(1)">
                <img src="../assets/tel.png" alt="telefone">
                <h3 class="app-tabs__tab-title">Recponsive Websites</h3>
            </button>
            <button class="app-tabs__item" @click="selectTab(2)">
                <img src="../assets/basket.png" alt="basket">
                <h3 class="app-tabs__tab-title">e Commerce Websites</h3>
            </button>
            <button class="app-tabs__item" @click="selectTab(3)">
                <img src="../assets/planet.png" alt="planet">
                <h3 class="app-tabs__tab-title">Daily blog Websites</h3>
            </button>
            <button class="app-tabs__item" @click="selectTab(4)">
                <img src="../assets/search.png" alt="search">
                <h3 class="app-tabs__tab-title">Search based Websites</h3>
            </button>

            <div v-if="currentTab == 1"
                 class="app-tabs_content">
                <img class="app-tabs_content-img" src="../assets/responsive.png" alt="responsive">
                <h3> Lorem Ipsum is simply dummy text</h3>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                     when an unknown printer took a galley of type and scrambled it to make a type
                     specimen book. It has survived not only five centuries, but also the leap into
                      electronic typesetting, remaining essentially unchanged.</p>

                <p>It was popularised in the 1960s with the release of Letraset sheets containing
                    Lorem Ipsum passages, and more recently with desktop publish ing software like
                    Aldus PageMaker including versions of Lorem Ipsum Lorem Ipsum is simply dummy
                     text only publishing
                     of the printing and typesetting indus try. Lorem Ipsum has been the industry's
                     standard dummy text ever since the 1500s, when an unknown printer took a galley
                     of type and scram bled it to make a type specimen book. It has survived not
                     five centuries, but also the leap into electronic typesetting, remaining
                     essentiallynged. It was popularised in the 1960s with the release of Letraset
                      sheets containing Lorem Ipsum passages, and more recently with desktop
                      software like Aldus PageMaker including versions of Lorem Ipsum.</p>
                </div>
            <div v-if="currentTab == 2"
                 class="app-tabs_content">
                <img class="app-tabs_content-img" src="../assets/ipad.png" alt="ipad">
                <h3>Lorem Ipsum is simply dummy text</h3>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                     when an unknown printer took a galley of type and scrambled it to make a type
                     specimen book. It has survived not only five centuries, but also the leap into
                      electronic typesetting, remaining essentially unchanged.</p>

                <p>It was popularised in the 1960s with the release of Letraset sheets containing
                    Lorem Ipsum passages, and more recently with desktop publish ing software like
                    Aldus PageMaker including versions of Lorem Ipsum Lorem Ipsum is simply dummy
                    text of the printing and typesetting indus try. Lorem Ipsum has been the
                    industry's standard dummy text ever since the 1500s, when an unknown printer
                     took a galley of type and scram bled it to make a type specimen book. It
                     has survived not only
                     five centuries, but also the leap into electronic typesetting, remaining
                     essentiallynged. It was popularised in the 1960s with the release of Letraset
                      sheets containing Lorem Ipsum passages, and more recently with desktop
                      publishing
                      software like Aldus PageMaker including versions of Lorem Ipsum.</p>
                </div>
            <div v-if="currentTab == 3"
                 class="app-tabs_content">
                <h3>3 Lorem Ipsum is simply dummy text</h3>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                     when an unknown printer took a galley of type and scrambled it to make a type
                     specimen book. It has survived not only five centuries, but also the leap into
                      electronic typesetting, remaining essentially unchanged.</p>

                <p>It was popularised in the 1960s with the release of Letraset sheets containing
                    Lorem Ipsum passages, and more recently with desktop publish ing software like
                    Aldus PageMaker including versions of Lorem Ipsum Lorem Ipsum is simply dummy
                     of the printing and typesetting indus try. Lorem Ipsum has been the industry
                     standard dummy text ever since the 1500s, when an unknown printer took a gal
                     of type and scram bled it to make a type specimen book. It has survived not
                     five centuries, but also the leap into electronic typesetting, remaining
                     essentiallynged. It was popularised in the 1960s with the release of Letraset
                      sheets containing Lorem Ipsum passages, and more recently with desktop
                      software like Aldus PageMaker including versions of Lorem Ipsum.</p>
                </div>
            <div v-if="currentTab == 4"
                 class="app-tabs_content">
                <h3>4 Lorem Ipsum is simply dummy text</h3>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                     when an unknown printer took a galley of type and scrambled it to make a type
                     specimen book. It has survived not only five centuries, but also the leap into
                      electronic typesetting, remaining essentially unchanged.</p>

                <p>It was popularised in the 1960s with the release of Letraset sheets containing
                    Lorem Ipsum passages, and more recently with desktop publish ing software lik
                    Aldus PageMaker including versions of Lorem Ipsum Lorem Ipsum is simply dummy
                     of the printing and typesetting indus try. Lorem Ipsum has been the industry's
                     standard dummy text ever since the 1500s, when an unknown printer took a galley
                     of type and scram bled it to make a type specimen book. It has survived not onl
                     five centuries, but also the leap into electronic typesetting, remaining
                     essentiallynged. It was popularised in the 1960s with the release of Letraset
                      sheets containing Lorem Ipsum passages, and more recently with desktop publish
                      software like Aldus PageMaker including versions of Lorem Ipsum.</p>
                </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'app-tabs',
  props: {
    value: String,
  },
  data() {
    return {
      currentTab: 1,
      tabItems: [{ id: 1 }],
    };
  },
  methods: {
    selectTab(selectedTab) {
      this.currentTab = selectedTab;
    },
  },
};

</script>

<style scoped>

.container {
  width: 1200px;
  margin: 0 auto;
}

.app-tabs {
    margin-top: 50px;
    text-align: center

}

.app-tabs__item {
    background: none;
    margin: 20px;
    border: none;
    border-radius: 20px;
    padding: 10px;
}

.app-tabs_content {
    background: #dbdada;
    border: none;
    border-radius: 20px;
    padding: 10px;
}

.app-tabs_content-img {
    width: 80%;
}

.app-tabs__item:hover {
    background: #dbdada;
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
    .app-tabs__item {
        background: none;
        margin: 5px;
        border: none;
        border-radius: 20px;
        padding: 5px;
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
