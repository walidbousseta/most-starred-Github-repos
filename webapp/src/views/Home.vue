<template>
  <div class="row">
    <h1>The most starred Github repos created in the last 30 days</h1>
  </div>
  <div class="row">
    <Card v-for="item in items" :="item" :key="item.id" />
    <p v-if="loading" style="text-align: center">Loading...</p>
    <p v-if="noMore" style="text-align: center">No more</p>
    <p v-if="error" style="text-align: center; color: red">
      There's an Error : {{ errorMsg }}
    </p>
    <Observer v-on:intersect="intersected" />
  </div>
</template>

<script>
import Observer from "@/components/Observer.vue";
import Card from "@/components/Cards.vue";
//import axios from "axios";

export default {
  name: "App",
  components: { Observer, Card },
  data() {
    return {
      page: 1,
      items: [],
      loading: false,
      noMore: false,
      error: false,
      errorMsg,
    };
  },
  computed: {
    disabled() {
      return this.loading;
    },
  },
  methods: {
    async intersected() {
      if (!this.noMore) {
        this.loading = true;

        var date = new Date();
        date.setDate(date.getDate() - 30);
        var beforToday = date.toISOString().split("T")[0];

        await fetch(
          `https://api.github.com/search/repositories?q=created:>${beforToday}&sort=stars&order=desc&page=${this
            .page++}&per_page=12`
        )
          .then((response) => response.json())
          .then((data) => {
            if (data.items) {
              this.items = [...this.items, ...data.items];
            } else {
              this.noMore = true;
            }
            this.loading = false;
          })
          .catch((error) => {
            console.log("Error : " + error);
            this.error = true;
            this.errorMsg = error.message;
          });
      }
    },
  },
};
</script>

<style>
</style>
