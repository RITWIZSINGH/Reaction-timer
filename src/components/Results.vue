<template>
  <p>Reaction Score: {{ score }} ms</p>
    <p class="rank">Your Rank: {{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if (this.score < 150) {
            this.rank = 'Elite Ninja';
        } else if (this.score < 250) {
            this.rank = 'Pro Ninja';
        } else if (this.score < 350) {
            this.rank = 'Average Ninja';
        } else {
            this.rank = 'Beginner Ninja';
        }
        console.log(`Your rank is: ${this.rank}`);
    }
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
}
</style>