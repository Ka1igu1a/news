<template>
  <div class="xl:container mx-auto">
    <h2 class="text-5xl my-[.8rem]">
      {{ pageTitle }}
    </h2>
    <hr class="border-solid border-t-2 mb-[1.6rem]" />
    <div class="grid grid-cols-2 gap-4">
      <template v-for="(cardInfo, index) in cards">
        <NewsListCard
          v-if="++index <= cardLimit"
          :key="index"
          :cardInfo="cardInfo"
        />
      </template>
    </div>
    <button v-if="cardsAmount > cardLimit" @click="cardLimit += 6">
      Показать еще
    </button>
  </div>
</template>

<script>
import NewsListCard from "@/components/NewsListCard.vue";

export default {
  name: "NewsList",
  props: ["pageTitle"],
  data: () => {
    return {
      cardLimit: 6,
      cards: '',
      currentPage: 1
    };
  },
  components: {
    NewsListCard,
  },

  created() {
      this.getNews()
  },

  methods: {
    async getNews() {
        const url = `https://domotekhnika.ru/api/v1/news?page=${this.currentPage}`
        this.cards = await (await fetch(url)).json().then((data) => data.data.news)
    },
  },
  computed: {
      cardsAmount() {
          const amount =  Object.keys(this.cards).length
          return amount
      }
  }
};
</script>