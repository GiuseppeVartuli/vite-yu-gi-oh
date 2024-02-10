<script>
import axios from "axios";
export default {
  name: "AppMain",
  data() {
    return {
      base_api_url: "https://db.ygoprodeck.com/api/v7/cardinfo.php",
      cards: [],
    };
  },
  computed: {
    nCards() {
      return this.cards.length ? this.cards.length : "";
    },
  },
  mounted() {
    console.log(this.base_api_url);
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => {
        console.log(response.data.data);
        this.cards = response.data.data;
        console.log(response.data.data.length);
        // console.log(response.data.data[0].name);
      });
  },
};
</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="counter">
          <p>Found {{ nCards }} cards</p>
        </div>
        <div class="card" v-for="card in cards">
          <img :src="card.card_images[0].image_url" alt="" />

          <div class="container_text">
            <p class="name">{{ card.name }}</p>
            <p class="category">{{ card.archetype }}</p>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.container {
  background: white;
  margin: 100px;
}
.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.counter {
  background: rgb(37, 34, 34);
  display: flex;
  align-items: center;
  width: 1520px;
  height: 60px;
  margin-top: 100px;
  & p {
    color: white;
    padding-left: 30px;
  }
}
.card {
  display: flex;
  flex-direction: column;
  width: calc(100% / 12 * 2.4) - 15px;
  padding: 15px;
  & img {
    width: 280px;
  }
  & .container_text {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background: orange;
    width: 280px;
    height: 197px;
  }
  .name {
    color: white;
    padding-bottom: 25px;
    text-align: center;
  }
}
</style>
