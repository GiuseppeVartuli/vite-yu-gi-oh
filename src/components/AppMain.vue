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
  mounted() {
    console.log(this.base_api_url);
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php")
      .then((response) => {
        console.log(response);
        console.log(response.data.data.name);
      });
  },
};
</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="counter">
          <p>Found -- cards</p>
        </div>
        <div class="card">
          <img
            src="https://www.cardtrader.com/uploads/blueprints/image/81905/show_blue-eyes-white-dragon-legendary-decks-ii-81905.png"
            alt=""
          />
          <div class="container_text">
            <p class="name">Drago Bianco Occhi Blue</p>
            <p class="category">Drago</p>
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
