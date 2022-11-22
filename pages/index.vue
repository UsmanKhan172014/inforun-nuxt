<template>
  <div class="container" id="grad">
    <div class="row">
      <div class="col-md-12 text-center">
        <h1><u>Welcome to Inforun</u></h1>
      </div>
    </div>

    <div class="row justify-content-center">

      <Cards v-for="card in cards" :key="card.id" :teamOne="card.teamOne" :teamTwo="card.teamTwo" :imgOne="card.imgOne"
        :imgTwo="card.imgTwo" :date="card.date" :time="card.time" :location="card.location">
      </Cards>

      <!-- iterate Cards component here -->

    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'IndexPage',
  data() {
    return {
      cards: []
    }
  },
  methods: {
    async addCard() {
      // const data= await fetch('https://superadmin.theskysportsnet.com/api/schedule/all');
      let data = await axios.get('https://superadmin.theskysportsnet.com/api/schedule/today');

      for (let i = 0; i < data.data.length; i++) {
        console.log(data.data[i])
        let temp=data.data[i];
        this.cards.push({
          id: temp.id,
          teamOne: temp.first_team,
          teamTwo: temp.second_team,
          imgOne: "https://superadmin.theskysportsnet.com/storage/"+temp.first_img,
          imgTwo: "https://superadmin.theskysportsnet.com/storage/"+temp.second_img,
          date: temp.match_date,
          time: temp.time,
          location: temp.venue,
        })
      }

    }
  },
  mounted() {
    this.addCard()
  }
}
</script>

<!-- <style scoped>

#grad {
  background-image: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet);
}
</style> -->
