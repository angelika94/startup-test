<template>
  <div class="graph">
    <div class="graph__header">
      <h2 class="graph__title">Daily Feedback Responses</h2>
      <div class="graph__settings row">
        <input type="text" placeholder="Month" value="December" class="graph__input graph__input--month">
        <input type="number" placeholder="Year" value="2018" class="graph__input graph__input--year">
        <button class="graph__input graph__input--chooser">
          <svg width="24" height="23" viewBox="0 0 24 23" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M19 3V1C19 0.447715 18.5523 0 18 0C17.4477 0 17 0.447715 17 1V3H19Z" fill="#1C3C55"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M7 3V1C7 0.447715 6.55228 0 6 0C5.44772 0 5 0.447715 5 1V3H7Z" fill="#1C3C55"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M3 23H21C22.6569 23 24 21.6569 24 20V7C24 5.34315 22.6569 4 21 4H3C1.34315 4 0 5.34315 0 7V20C0 21.6569 1.34315 23 3 23ZM2 9H22V20C22 20.5523 21.5523 21 21 21H3C2.44772 21 2 20.5523 2 20V9Z" fill="#1C3C55"/>
            <rect x="4" y="11" width="4" height="3" fill="#1C3C55"/>
            <rect x="10" y="11" width="4" height="3" fill="#1C3C55"/>
            <rect x="4" y="16" width="4" height="3" fill="#1C3C55"/>
            <rect x="10" y="16" width="4" height="3" fill="#1C3C55"/>
            <rect x="16" y="11" width="4" height="3" fill="#1C3C55"/>
          </svg>
        </button>
      </div>
    </div>
    <div class="graph__wrapper">
      <ul class="graph__body">
        <li v-for="(item, index) in graphData"
            :key="index"
            :data-day="item.day"
            :style="{ height: item.value + '%', maxWidth: 100 / 2.5 / graphData.length + '%'}"
            class="graph__bar"></li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        graphData: [
          { day: 1, value: 15.2 },
          { day: 2, value: 32 },
          { day: 3, value: 45 },
          { day: 4, value: 7  },
          { day: 5, value: 32 },
          { day: 6, value: 45 },
          { day: 7, value: 26 },
          { day: 8, value: 35.6 },
          { day: 9, value: 10.6 },
          { day: 10, value: 42 },
          { day: 11, value: 21 },
          { day: 12, value: 64.4 },
          { day: 13, value: 32 },
          { day: 14, value: 45 },
          { day: 15, value: 6.21 },
          { day: 16, value: 21 },
          { day: 17, value: 15.6 },
          { day: 18, value: 42 },
          { day: 19, value: 21 },
          { day: 20, value: 35 },
          { day: 21, value: 20 },
          { day: 22, value: 15 },
          { day: 23, value: 28 },
          { day: 24, value: 50 },
          { day: 25, value: 40 },
          { day: 26, value: 80 },
          { day: 27, value: 70 },
          { day: 28, value: 55 },
          { day: 29, value: 60 },
        ]
      }
    }
  }
</script>
<style lang="scss">
@import '../assets/scss/settings';
.graph {
  margin: 2rem 2.37rem;;
  padding: 0 1.5rem 3rem;
  border-radius: .25rem;
  -webkit-box-shadow: 1px 1px 3px 0 rgba(0,0,0,0.5);
  -moz-box-shadow: 1px 1px 3px 0 rgba(0,0,0,0.5);
  box-shadow: 1px 1px 3px 0 rgba(0,0,0,0.5);

  &__header {
    padding: 1.5rem 2rem 1rem;
    display: flex;
    justify-content: space-between;
  }

  &__title {
    margin-left: 10%;
    font-size: 1.25rem;
    color: #1C3C55;
  }

  &__settings {
    display: flex;
    align-items: center;
  }

  &__input {
    margin-left: .6rem;
    &--month {
      max-width: 7.5rem;
    }

    &--year {
      max-width: 5.6rem;
    }

    &--chooser {
      padding: 0;
      border: none;
      background-color: transparent;
    }
  }

  &__wrapper {
    padding-bottom: 35%;
    position: relative;
  }

  &__body {
    padding: 0 1rem;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    border-top: .06rem solid #EAEDF3;
    border-bottom: .06rem solid #EAEDF3;
    background-image: repeating-linear-gradient(to top,
      rgb(255, 255, 255),
      rgb(255, 255, 255) 33%,
      rgb(234, 237, 243) 33.7%);
  }

  &__bar {
    max-width: 1.5em;
    background-color: #9DC2D4;
    flex: 1;
    list-style-type: none;
    position: relative;
    border-top-left-radius: .125rem;
    border-top-right-radius: .125rem;
    &:hover {
      background-color: #1C3C55;
    }
    &::after {
      content: attr(data-day);
      width: 100%;
      position: absolute;
      bottom: -.8rem;
      display: block;
      text-align: center;
      color: #9EA0A5;
      font-size: .5rem;
      @media (min-width: $lg) {
        bottom: -1.5rem;
        font-size: .75rem;
      }
    }
  }
}
</style>

