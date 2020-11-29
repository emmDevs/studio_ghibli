<template>
    <div class="cast-list">

        <film-cast-item v-for="(person, index) in people" :people="people" :key="index"></film-cast-item>
        

    </div>
</template>

<script>
export default {
    name: 'film-cast',
    props: ["people"],
}
</script>

<style>

</style>