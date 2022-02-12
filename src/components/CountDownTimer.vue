<template>
  <div class="ContDownTimer">
    {{ daysToCountTo }}
    {{ hoursToCountTo }}
    {{ minutesToCountTo }}
    {{ secondsToCountTo }}

    {{ dateToCountTo }}
  </div>
</template>

<script>
export default {
  name: 'CountDownTimer',
  components: {},
  data: function () {
    return {
      dateToCountTo: null,
      daysToCountTo: null,
      hoursToCountTo: null,
      minutesToCountTo: null,
      secondsToCountTo: null,
    };
  },
  methods: {
    getTimeToDeadlineDate() {
      var countDownDate = new Date('March 1, 2022 12:00:00').getTime();
      countDownDate = Math.floor(countDownDate + 691200000); // for Livedemo always current date + 8 days
      var now = new Date().getTime();
      var distance = countDownDate - now;
      var days = Math.floor(distance / (1000 * 60 * 60 * 24));
      var hours = Math.floor(
        (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
      );
      var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      var seconds = Math.floor((distance % (1000 * 60)) / 1000);
      this.daysToCountTo = days;
      this.hoursToCountTo = hours;
      this.minutesToCountTo = minutes;
      this.secondsToCountTo = seconds;
    },

    setDeadlineDate() {
      setInterval(this.getTimeToDeadlineDate, 1000);
    },
  },
  created() {
    this.setDeadlineDate();
  },
};
</script>

<style scoped></style>
