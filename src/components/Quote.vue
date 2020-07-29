<template>
  <v-card class="mx-auto my-4" max-width="600px" max-height="600px" dark>
    <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg">
      <v-card-title align="center" class="mt-8">"{{selectedQuote.quote}}"</v-card-title>
      <v-spacer></v-spacer>
      <h3 style="position:absolute;top:50%;right:15px;color:white">Hazrat Muhammad (SAW)</h3>
    </v-img>
    <v-card-actions>
      <v-spacer></v-spacer>
      <v-btn color="primary" @click="nextQuote">next quote</v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  data: () => ({
    selectedQuote: {
      quote: "",
      bgImg: ""
    },
    quotes: [
      {
        quote:
          "The best among you is the one who doesn’t harm others with his tongue and hands",
        bgImg: "https://unsplash.com/photos/Y9bC2h5V9c8"
      },
      {
        quote:
          "I leave behind me two things, The Quran and My Sunnah and if you follow these you will never go astray",
        bgImg: "https://unsplash.com/photos/Dbdu_Y56ou4"
      },
      {
        quote: "Do not waste water even if you were at a running stream",
        bgImg: "https://unsplash.com/photos/uc9GjDHj1yA"
      },
      {
        quote: "Modesty brings nothing except good",
        bgImg: "https://unsplash.com/photos/pwMbtwA9LRc"
      },
      {
        quote:
          "Richness is not having many belongings, but richness is contentment of the soul",
        bgImg: "https://unsplash.com/photos/qun1Pdo6wIM"
      },
      {
        quote: "There is reward for kindness to every living thing.",
        bgImg: "https://unsplash.com/photos/qaZofx5ePm8"
      },
      {
        quote:
          "The best among you are those who have the best manners and character.",
        bgImg: "https://unsplash.com/photos/WzUyHyR3ByY"
      },
      {
        quote: "Seek knowledge from cradle to the grave.",
        bgImg: "https://unsplash.com/photos/OOVtg-y6bTw"
      },
      {
        quote:
          "Verily, Allah is mild and is fond of mildness, and He gives to the mild what He does not give to the harsh.",
        bgImg: "https://unsplash.com/photos/ZDinhtHTxeE"
      },
      {
        quote:
          "He, who wishes to enter paradise at the best gate, must please his father and mother.",
        bgImg: "https://unsplash.com/photos/GT8IKQvx9xc"
      },
      {
        quote:
          "He who has in his heart the weight of a mustard seed of pride shall not enter paradise.",
        bgImg: "https://unsplash.com/photos/hiNjvPba1Jc"
      },
      {
        quote:
          "Kindness is a mark of faith and whoever is not kind has no faith.",
        bgImg: "https://unsplash.com/photos/BCF7cHvc778"
      }
    ]
  }),
  created() {
    console.log(this.quotes[0]);
    this.selectedQuote = Object.assign({}, this.quotes[1]);
    console.log(this.selectedQuote);
    setInterval(() => {
      this.nextQuote();
    }, 7000);
  },
  methods: {
    nextQuote() {
      //console.log(this.selectedQuote);
      let quote = this.quotes[Math.floor(Math.random() * this.quotes.length)];
      this.selectedQuote = Object.assign({}, quote);
      console.log(this.selectedQuote);
    }
  }
};
</script>