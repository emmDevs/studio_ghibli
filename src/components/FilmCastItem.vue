<template>
  <div class="film-cast-item">
        <h1 class="name">{{person.name}}</h1>
        <!-- <film-image :film="film"></film-image> -->
    </div>
</template>

<script>
export default {
    name: 'film-cast-item',
    props: ['person'],

}
</script>

<style>

</style>