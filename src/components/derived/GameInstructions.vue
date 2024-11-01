<script>
import pumpkinPath from '@/assets/Gifs/pumpkin-path.gif';
import patty from '@/assets/images/party.png';
import kissBeam from '@/assets/images/kiss-beam.png';
import ghost from '@/assets/images/ghost_9.png';
import lollipop from '@/assets/images/lollipop.png';

export default {
    nome: 'GameInstructions',
    data() {
        return {
            pumpkinPath,
            name: '',
            patty,
            kissBeam,
            ghost,
            lollipop,
        };
    },
    methods: {
        submitForm() {
            this.$emit('name-submitted', this.name);
            this.name = '';
        },
    },
};
</script>

<template>
    <section class="presentation-container">
        <section class="presentation-text">
            <h2>Bem-vindo ao jogo mais divertido do Halloween!
                <img :src="patty" alt="Patty icon" class="patty-icon">
            </h2>
            <p>Para começar, insira seu nome e clique em "OK" para entrar no clima! </p>
            <p>Em seguida, prepare-se para uma aventura cheia de surpresas:
                você só precisa clicar no caldeirão e arrastar o que encontrar — mas cuidado, nem
                tudo é doce! 
                <img :src="kissBeam" alt="kiss Beam" class="kiss-beam-icon icon">
            </p>
            <p>Cada item retirado do caldeirão é uma surpresa: pode ser um doce
                delicioso ou uma travessura assustadora!
                Continue até estar satisfeito ou decida parar para ver o resultado final.
                No fim, descubra quantos doces e quantas travessuras você acumulou!
            </p>
            <p class="finaly-text-p">Então, está pronto para se surpreender? Vamos jogar!
                <span class="icon-box">
                    <img :src="ghost" alt="Ghost" class="ghost-icon icon">
                    <img :src="lollipop" alt="Lollipop" class="lollipop-icon icon">
                </span>
            </p>
        </section>
        <section class="name-container">
            <img :src="pumpkinPath" alt="pumpkin-path" class="pumpkin-path">
            <form @submit.prevent="submitForm" class="form-container">
                <input type="text" id="name" v-model="name" placeholder="Seu nome" @keyup.enter="submitForm" required />
                <button type="submit">OK</button>
            </form>
        </section>
    </section>
</template>

<style>
.presentation-container {
    padding: 3rem;
    margin: 1rem auto;
    max-width: 53rem;
    min-height: 32rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
    background-color: var(--vt-c-indigo);
    opacity: 1.0;
    border-radius: 0.625rem;
    box-shadow: 2px 4px 4px #FFA726;
    color: #2E1A47;
}

.presentation-text {
    line-height: 1.6rem;
    text-align: start;
    text-indent: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1.2rem;

}

h2 {
    -webkit-text-stroke-width: 0.1rem;
    -webkit-text-stroke-color: orange;
    color: #2E1A47;
    font-weight: 500;
    margin-bottom: 1.3rem;
}

.patty-icon {
    width: 2.5rem;
}

.name-container {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: start;
    padding: 0 4rem;
    gap: 3rem;
}

.pumpkin-path {
    width: 7rem;
    top: 0;
}

.finaly-text-p {
    display: flex;
}

.icon-box {
    display: flex;
    padding-left: 0.2rem;
}

.icon {
    width: 2rem;
    margin-left: 0.2rem;
}

.form-container {
    display: flex;
    gap: 0.25rem;
}

input,
button {
    margin: 0.8rem 0;
    padding: 1rem 1rem;
    font-size: 1rem;
    border-radius: 0.5em;
}

button {
    padding: 1rem 2rem;
    background-color: #FFA726;
    color: #FFFFFF;
    font-weight: 800;
    -webkit-text-stroke-width: 1.2px;
    -webkit-text-stroke-color: #000;
}
</style>
