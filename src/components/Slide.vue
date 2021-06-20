<template>
  <div class="slide-card">
    <!-- :src="details.user.profile_image" // image src -->
    <div class="slide-img-wrapper">
      <img
        class="slide-img"
        src="https://picsum.photos/seed/dog/500/600"
        alt="user-image"
      />
    </div>
    <h1 class="slide-title">
      {{ `${details.user.first_name} ${details.user.last_name}` }}
    </h1>
    <p class="slide-date">{{ formattedDate }}</p>
  </div>
</template>

<script>
import moment from "moment";

export default {
  props: {
    details: Object,
  },
  computed: {
    formattedDate: function() {
      return moment(this.details.user.created_at).format("MMMM DD, YYYY");
    },
  },
};
</script>

<style scoped>
.slide-card {
  display: flex;
  flex-direction: column;
  padding-bottom: 80px;
}

.slide-img-wrapper {
  height: 440px;
  width: 345px;
  overflow: hidden;
  display: "flex";
  justify-content: center;
  align-items: center;
}

.slide-img {
  height: 100%;
  width: 100%;
  transition: all 1s;
  cursor: pointer;
}

.slide-img:hover {
  transform: scale(1.1);
}

.slide-title {
  color: #868e96;
  text-align: center;
  font-size: 20px;
  margin: 0;
  margin-top: 35px;
  cursor: pointer;
}

.slide-title:hover {
  color: #ea1f5e;
}

.slide-date {
  color: #868e96;
  padding: 0;
  margin-top: 5;
  text-align: center;
  font-size: 15px;
}
</style>
