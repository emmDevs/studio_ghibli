<template>
    <div class="film-list-item">
        <h1>{{film.title}}</h1>
        <film-image :film="film"></film-image>
    </div>
</template>

<script>
export default {
    name: 'film-list-item',
    props: ['film']
}
</script>

<style>

</style>