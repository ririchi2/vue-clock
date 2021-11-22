<template>
    <div :class="actualTheme" class="clock">
        <h1>{{ time }}</h1>
    </div>
    <button @click="changeTheme">☀</button>
</template>

<script>
    export default {
        name: "VueClock",
        data() {
            return {
                time: "00:00:00",
                audio: null,
                actualTheme: "light",
            }
        },
        methods: {
            getTime() {
                setInterval(() => {
                    this.time = new Date().toTimeString().split(" ")[0];
                } ,1000);
            },
            changeTheme() {
                if(this.actualTheme === "dark") {
                    this.actualTheme = "light"
                } else {
                    this.actualTheme = "dark"
                }
            },
        },
        mounted() {
            this.getTime();
            this.audio = new Audio("https://ia800503.us.archive.org/8/items/futuresoundfx-98/futuresoundfx-13.mp3");
        },
        watch: {
            time() {
                this.audio.play();
            },
        },
    }
</script>

<style>
    .clock {
        padding: 0.1em;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 0.5em;
        font-size: 3em;
        font-family: 'Quantico', sans-serif;
    }
    .light {
        background: pink;
        color: black;
        border: 1em solid gray;
    }
    .dark {
        background: black;
        color: red;
        border: 1em solid gray;
    }

</style>