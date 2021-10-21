<template>
  <div id="counter-container">
    <div class="counter-header">
      <h1 v-if="!expired">Мы скоро откроемся!</h1>
      <h2 v-else>
        Мы успешно открылись! Вы можете перейти на наш сайт по этой ссылке
        "LINK"
      </h2>
    </div>
    <div v-if="!expired" class="wrapper">
      <div class="counter-part">
        <h2>{{ days }} :</h2>
        <p>День</p>
      </div>
      <div class="counter-part">
        <h2>{{ hours }} :</h2>
        <p>Часы</p>
      </div>
      <div class="counter-part">
        <h2>{{ minutes }} :</h2>
        <p>Минут</p>
      </div>
      <div class="counter-part">
        <h2>{{ seconds }}</h2>
        <p>Секунды</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["year", "month", "date", "hour", "minute", "second", "millisecond"],
  data() {
    return {
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
      expired: false,
    };
  },
  computed: {
    _seconds() {
      return 1000;
    },
    _minutes() {
      return this._seconds * 60;
    },
    _hours() {
      return this._minutes * 60;
    },
    _days() {
      return this._hours * 24;
    },
    end() {
      return new Date(
        this.year,
        this.month,
        this.date,
        this.hour,
        this.minute,
        this.second,
        this.millisecond
      );
    },
  },
  methods: {
    formatNumber: (num) => (num < 10 ? "0" + num : num),
    showRemaining() {
      const timer = setInterval(() => {
        const now = new Date();
        // const end = new Date(2021, 11, 21, 0, 0, 0, 0);
        const distance = this.end.getTime() - now.getTime();

        if (distance < 0) {
          clearInterval(timer);
          this.expired = true;
          return;
        }

        const days = Math.floor(distance / this._days);
        const hours = Math.floor((distance % this._days) / this._hours);
        const minutes = Math.floor((distance % this._hours) / this._minutes);
        const seconds = Math.floor((distance % this._minutes) / this._seconds);
        this.seconds = this.formatNumber(seconds);
        this.minutes = this.formatNumber(minutes);
        this.hours = this.formatNumber(hours);
        this.days = this.formatNumber(days);
      }, 1000);
    },
  },
  mounted() {
    this.showRemaining();
    // setTimeout(() => (this.loaded = true), 3500);
  },
};
</script>

<style scoped>
#counter-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: brown;
  padding: 2px;
  opacity: 0;
  animation: btn 3s ease forwards 2s;
  transition: transform 1s ease;
}
.wrapper {
  display: flex;
}
.counter-part {
  margin: 8px;
}
h1 {
  font-size: 2.4rem;
  color: #e2b370;
}
@keyframes btn {
  to {
    opacity: 1;
  }
}
@media screen and (max-width: 765px) {
  h1 {
    font-size: 1.8rem;
  }
}
</style>
