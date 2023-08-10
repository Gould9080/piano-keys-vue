<template>
    <div id="card">
        {{ this.number }}
    </div>
</template>

<script>
export default {
    name: "square-tile",
    props: ["box"],
    data() {
        return {
            number: this.box.number,
        }
    }
}
</script>

<style>
#card {
    height: 250px;
    width: 250px;
    border: 1px solid red;
    margin: 5px;
}
</style>