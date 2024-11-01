<script>
import GameInstructions from './GameInstructions.vue';

export default {
    components: {
        GameInstructions,
    },
    data() {
        return {
            userName: 'Visitante',
            candyCount: 0,
            trickCount: 0,
        };
    },
    methods: {
        updateName(name) {
            this.userName = name;
        },
    },
};
</script>

<template>
    <div>
        <AppHeader :userName="userName" :candyCount="candyCount" :trickCount="trickCount" />
        <GameInstructions @name-submitted="updateName" />
    </div>
</template>