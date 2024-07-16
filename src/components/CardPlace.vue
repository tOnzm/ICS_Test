<template>
  <v-col>
    <div class="card-place">
      <v-row class="card-top">
        <img :src="profileImg" alt="Profile Image" class="profile-img" />
        <v-row class="card-detail">
          <h6>{{ placeName }}</h6>

          <v-col class="time-rating">
            <h6 class="time">
              <font-awesome-icon icon="fa-solid fa-calendar-days" /> {{ openTime }} -
              {{ closeTime }}
            </h6>
            <h6 class="rating"><font-awesome-icon icon="fa-solid fa-circle" /> {{ rating }}</h6>
          </v-col>
        </v-row>
      </v-row>
      <v-row class="thumbnail">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image"
          alt="Image"
          class="profile-img"
          width="120"
          height="120"
        />
      </v-row>
    </div>
  </v-col>
</template>

<script>
export default {
  name: 'CardPlace',
  props: {
    placeName: String,
    openTime: String,
    closeTime: String,
    rating: Number,
    profileImg: String,
    images: Array
  }
}
</script>

<style scoped>
.card-place {
  background-color: var(--white);
  width: 400px;
  height: 225px;
  padding: 16px;
  border-radius: 10px;
  box-shadow: #00000025 0px 3px 3px 0px;
}
.card-top img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  border-radius: 10px;
}
.card-top {
  display: flex;
  width: 100%;
  gap: 16px;
  padding-bottom: 8px;
}
.card-detail {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-content: space-between;
}

.time-rating {
  display: flex;
  justify-content: space-between;
  gap: 140px;
  align-items: center;
}
.time {
  font-size: 14px;
  font-weight: 400;
  line-height: 20.02px;
  display: flex;
  align-items: stretch;
  gap: 4px;
  letter-spacing: 0.15px;
}
.rating {
  color: var(--primary-color);
  font-size: 16px;
  font-weight: 500;
  line-height: 24px;
  letter-spacing: 0.15px;
  align-items: center;
  gap: 4px;
  display: flex;
}
.thumbnail {
  border-radius: 10px;
  overflow: hidden;
  display: flex;
}
.thumbnail img {
  object-fit: cover;
}
</style>
