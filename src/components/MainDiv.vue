
<template>
    <div id="maindiv">
        <div id="header">
            <h1>EAT A BROG</h1>
            <h2>Eat a bean</h2>
            <button @click="newBox">New Box</button>
        </div>
        <div id="body">
            <SquareTile v-for="b in this.boxes" v-bind:key="b.number" v-bind:box="b" />
        </div>
    </div>
</template>

<script>
import SquareTile from './SquareTile.vue'
export default {
    name: "main-div",
    components: {
        SquareTile
    },
    props: {

    },
    data() {
        return {
            number: 0,
            boxes: [],
        };
    },
    computed: {

    },
    methods: {
        newBox() {
            this.number++;
            this.boxes.push({ number: this.number });
            console.log("NEW BOX ", this.number)
        }
    }
}
</script>

<style scoped>
#maindiv {
    height: 100vh;
}

#body {
    display: flex;
    flex-wrap: wrap;
    padding: 10px;
}

h1 {
    margin: 0;
}
</style>