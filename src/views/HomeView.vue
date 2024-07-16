<template>
  <main>
    <v-row class="title">
      <v-col><h4>Place List</h4></v-col>
      <v-col class="action-tools">
        <select class="filter">
          <option value="All">All</option>
          <option value="Restaurant">Restaurant</option>
          <option value="Bakery">Bakery</option>
          <option value="Cafe">Cafe</option>
        </select>

        <input type="text" placeholder="Search name..." class="search-box" />
      </v-col>
    </v-row>

    <v-row class="card-display">
      <CardPlace
        v-for="place in places"
        :key="place.id"
        :place="place"
        :placeName="place.name"
        :openTime="place.operation_time[1].time_open"
        :closeTime="place.operation_time[1].time_close"
        :rating="place.rating"
        :profileImg="place.profile_image_url"
        :images="place.images"
      />
    </v-row>
  </main>
</template>

<script>
import CardPlace from '../components/CardPlace.vue'

export default {
  name: 'HomePage',

  data() {
    return {
      places: []
    }
  },

  async mounted() {
    try {
      const response = await fetch('/src/data/example_data.json')
      this.places = await response.json()
    } catch (error) {
      console.error('Error ', error)
    }
  },

  components: {
    CardPlace
  }
}
</script>

<style>
main {
  display: flex;
  flex-direction: column;
  padding: 24px 16px 0px 114px;
}
.title {
  display: flex;
  justify-content: space-between;
  padding: 16px 0;
}
.card-display {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
}

.search-box {
  width: 400px;
  height: 40px;
  border-radius: 50px;
  border: 1px solid #134b8a;
  padding: 8px;
  color: #00000054;
}
.filter {
  width: 185px;
  height: 40px;
  border-radius: 50px;
  padding: 8px;
  border: 1px solid #134b8a;
  color: #00000054;
}
.action-tools {
  gap: 16px;
  display: flex;
}

@media only screen and (max-width: 600px) {
  .filter {
    width: 100%;
    height: 31px;
  }
  .title {
    flex-direction: column;
    gap: 16px;
  }
  .action-tools {
    flex-direction: column;
  }
  .search-box {
    width: 100%;
    height: 31px;
  }
  main {
    padding: 16px;
  }
}
</style>
