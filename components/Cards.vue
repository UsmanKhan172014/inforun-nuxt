<template>
  <div class="col-md-4 mt-2">
    <div class="card">
      <div class="card-header text-center">
        <h3 class="card-title">{{ teamOne }} vs {{ teamTwo }}</h3>
      </div>
      <div class="card-body">
        
        <div class="row">
            <div class="col-md-6 text-center mt-2">
                <img :src="imgOne" width="100px" alt="" class="img-fluid">
            </div>
            <div class="col-md-6 text-center  mt-2">
                <img :src="imgTwo" width="100px" alt="" class="img-fluid">
            </div>
        </div>
        <div class="row">
            <div class="col-md-12 text-center mt-4">
                <h4><u>Venue : {{ location }}</u></h4>
            </div>
        </div>
        <div class="row mt-2">
            <div class="col-md-6 text-center">
                <h5>Date : {{ date }}</h5>
            </div>
            <div class="col-md-6 text-center">
                <h5>Time : {{ time }}</h5>
            </div>
            </div>
      </div>
      <div class="row p-3">
        <div class="col-md-12 text-center">
          <NuxtLink to="/login" class="btn btn-secondary">Watch Live</NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Card',
  props: {
    teamOne: {
      type: String,
      required: true,
    },
    teamTwo: {
      type: String,
      required: true,
    },
    imgOne: {
      type: String,
      required: true,
    },
    imgTwo: {
      type: String,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
    time: {
      type: String,
      required: true,
    },
    location: {
      type: String,
      required: true,
    },

  },
}
</script>
