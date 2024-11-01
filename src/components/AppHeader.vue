<script scoped>
import candyIcon from '@/assets/images/lollipop.png';
import trickIcon from '@/assets/images/witch.png';
import DisplayComponent from './derived/DisplayComponent.vue';

export default {
    name: "AppHeader",

    props: {
        userName: {
            type: String,
            default: 'Visitante',
        },
        candyCount: {
            type: Number,
            default: 0,
        },
        trickCount: {
            type: Number,
            default: 0,
        },
      component: {
        DisplayComponent,
      }
    },
    data() {
        return {
            candyIcon,
            trickIcon,
        };
    }
};

</script>

<template>
    <header class="container-header">
        <div class="user-info box-icon">
            <div class="icon circle"></div>
            <span class="user-name">{{ userName }}</span>
            <DisplayComponent />
        </div>
        <div class="container-counter">
            <div class="candy-info box-icon">
                <img :src="candyIcon" alt="Candy Icon" class="icon candy-icon" />
                <span class="counter"> {{ candyCount }}</span>
            </div>
            <div class="trick-info box-icon">
                <img :src="trickIcon" alt="Trick Icon" class="icon trick-icon" />
                <span class="counter"> {{ trickCount }} </span>
            </div>
        </div>
    </header>
</template>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        place-items: start;
        z-index: 1;
    }
    .box-icon {
        display: flex;
        flex-direction: row;
        align-items: center;
        line-height: 1rem;
        min-width: 5rem;
        gap: 0.4rem;
    }
    .icon {
        width: 1em;
    }
    .circle {
        border-radius: 50%;
        background-color: #FFA726;
        height: 1rem;
        width: 1rem;
        margin-right: 0.3rem;
    }
    .container-counter {
        display: flex;
        flex-direction: wrap;
        justify-content: space-around;
        align-items: center;
    }
</style>