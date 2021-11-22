<template>
    <div class="container">
        <VueClock/>
    </div>
</template>

<script>
    import VueClock from "./components/VueClock.vue";

    export default {
        name: "App",
        components: {
            VueClock: VueClock
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quantico&display=swap');
</style>