<template>
  <div class="slider-container">
    <v-carousel>
      <v-carousel-item v-for="(item, index) in sliderItems" :key="index">
        <div class="slider-item">
          <lottie-animation
              :path="item.animationUrl"
          />
          <div class="slider-text">
            <h2>{{ item.title }}</h2>
          </div>
        </div>
      </v-carousel-item>
    </v-carousel>
    <div class="container">
      <img src="Digiit.png" alt="Digiit logo">
      <div class="presentation">
        <h1>Digiit</h1>
        <div class="text-presentation">
          <p>This is a project for school.</p>
          <p>It's an application that allows you to manage effectively
            clocking purchasing documents, while offering functionalities
            analysis of the latter.</p>
            <p>The application, called "Digiit", aims to facilitate the management
            Purchase documents for users while providing a view
            of their overall purchasing habits.</p>
            <p>The 'tickets' correspond to the receipts while the
            'wallets' collect vouchers, loyalty cards or any other
            Similar document that the user would like to categorize differently.</p>
            <p>As you have seen this application got five importants functionnalities.</p>
        </div>
      </div>
    </div>
  <div class="functionnalities">
    <h1>Functionnalities :</h1>
    <div v-for="(item,i) in functionnalitiesItems" :key="i">
      <img :src="item.imageUrl" :alt="item.title">
    <div>
    <div>
      <h2> {{ item.title }} </h2>
      <p> {{ item.comment }} </p>
    </div>
    </div>
  </div>
  </div>
</div>
</template>

<script>
import LottieAnimation from "lottie-vuejs/src/LottieAnimation.vue";

export default {
  components: {
      LottieAnimation
  },
  data() {
    return {
      sliderItems: [
        {
          animationUrl: 'documents.json',
          title: 'Centralization of documents',
        },
        {
          animationUrl: 'photo.json',
          title: 'Capturing a new document',
        },
        {
          animationUrl: 'budget.json',
          title: 'Budget monitoring',
        },
        {
          animationUrl: 'balance.json',
          title: 'Balance sheet according to periods',
        },
        {
          animationUrl: 'evaluation.json',
          title: 'Evaluation of documents',
        },
      ],
      functionnalitiesItems: [
        {
          imageUrl: 'centralize.png',
          title: 'Centralization of documents',
          comment: 'Gather all documents saved by the user in a single and the same place, thus facilitating the management of its purchases and the Reduction of paper waste'
        },
        {
          imageUrl: 'capture.png',
          title: 'Capturing',
          comment: 'Render in photo or save a new document, such as a receipt or invoice, in order to store it in the application\'s database.'
        },
        {
          imageUrl: 'budget.png',
          title: 'Budget monitoring',
          comment: 'Visualize its expenditure data in the form of graphs andtables, in order to better understand your purchasing habits and takeclearer decisions on the management of its finance.'
        },
        {
          imageUrl: 'balance.png',
          title: 'Balance sheet',
          comment: 'Define periods of time for which he wishes to see a summary of his expenditure.'
        },
        {
          imageUrl: 'notes.png',
          title: 'Evaluation of documents',
          comment: 'Note the different products or merchants in order to evaluate the qualities and defects.'
        },
      ]
    };
  },
  name: 'IndexPage',
};
</script>

<style>
.lottie-player {
  display: block;
  margin: 0 auto;
  position: absolute;
  left: 11%;
  z-index: -10;
}

.slider-item {
  position: absolute;
  height: 60vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.slider-text {
  position: absolute;
  top: 70%;
  left: 50%;
  width: max-content;
  transform: translate(-50%, 70%);
  text-align: center;
  color: #ffffff;
  z-index: 1;
}

.slider-text h2 {
  font-size: 2.5em;
  font-weight: 400;
  text-shadow: 2px 2px #000000;
  background-color: #00000032;
}

.container img {
  width: 150px;
  height: 170px;
  padding-top: 18px;
}

.container {
  display: grid;
  place-items: center;
}

.presentation {
  text-align: center;
  padding: 30px;
}

.text-presentation {
  padding-top: 20px;
  text-align: left;
}

.functionnalities > div {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 20px;
}

.functionnalities img {
  margin-right: 60px;
  margin-left: 20%;
  width: 200px;
  height: 220px;
  border-radius: 20%;
}

.functionnalities > div > h2 {
  text-align: center;
  margin-bottom: 10px;
}

.functionnalities p {
  margin: 2px 15px 0 0;
  width: 75%;
}

.functionnalities h1 {
  text-align: center;
  margin-bottom: 30px;
}

.functionnalities div,
.functionnalities img{
  margin-bottom: 30px;
}

.functionnalities h1 {
  text-align: center;
  margin-bottom: 50px;
}
</style>
