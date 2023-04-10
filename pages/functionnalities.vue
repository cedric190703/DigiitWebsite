<template>
  <div class="container">
    <div class="items">
      <div class="item" v-for="(item, index) in funcItems" :key="index">
        <div class="item-header">
          <h2 class="item-title">{{ item.title }}</h2>
        </div>
        <div class="item-body">
          <div class="item-image">
            <img :src="item.imageURL" alt="item image" @mouseover="hover(item)" @mouseleave="leave(item)">
            <div class="item-comments" :class="{ 'active': item.active }">
              <p>{{ item.comments }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      funcItems: [
        {
          title: 'Home page',
          comments: 'The main page of our application is where users can view all the tickets they have submitted on the application. As you can see in the screenshot, this page displays a list of all the tickets created by the user, as well as their current status. In addition to viewing existing tickets, users can also create new tickets from this page. We offer several methods of ticket creation to provide an optimal user experience. Users can take a photo of the item, select an image from their gallery, upload files, or even use OCR technology to automatically capture information. Furthermore, users can choose to filter the different documents, such as sorting them in ascending order by date or price.',
          imageURL: 'tickets.png',
          active: false,
        },
        {
          title: 'Wallets page',
          comments: 'Allows users to store vouchers or purchase orders in a page similar to that of tickets. To add documents to this page, we have the same options as for tickets except that OCR is only available for tickets. For this part, we simply need to add and delete documents.',
          imageURL: 'wallets.png',
          active: false,
        },
        {
          title: 'Data page',
          comments: 'Allows users to view various graphs such as pie charts and line graphs. To add graphs to this page, the user must select between two dates and graphs are generated based on the user\'s data. We have implemented 8 different selectable graphs.',
          imageURL: 'graphs.png',
          active: false,
        },
        {
          title: 'Menu screen',
          comments: 'the user can access the menu page which allows them to access various information such as their personal data, financial statement, and other information related to the application such as privacy settings, configurations, and help. Additionally, the application has a progress bar that displays the current usage percentage relative to an amount set by the user. This feature allows the user to better control their expenses by setting monthly goals.',
          imageURL: 'bilan.png',
          active: false,
        },
      ],
    }
  },
  methods: {
    hover(item) {
      item.active = true;
    },
    leave(item) {
      item.active = false;
    },
  },
}
</script>

<style scoped>
.title {
  text-align: center;
  margin-bottom: 40px;
  font-size: 40px;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

.items {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.item {
  width: calc(50% - 10px);
  margin-bottom: 20px;
  border-radius: 5px;
  transition: transform 0.2s ease-in-out;
  position: relative;
  overflow: hidden;
}

.item:hover {
  transform: translateY(-5px);
}

.item:hover .item-comments {
  opacity: 1;
}

.item-image {
  position: relative;
}

.item-image img {
  width: 100%;
  height: auto;
  display: block;
}

.item-title {
  text-align: center;
  margin: 27px;
}

.item-comments {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  opacity: 0;
  transition: opacity 0.2s ease-in-out;
  background-color: rgba(0, 0, 0, 0.8);
  color: #fff;
  padding: 10px;
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  overflow: auto;
}

.item-comments p {
  margin: 0;
}
</style>
