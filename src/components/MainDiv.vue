
<template>
    <div id="maindiv">
        <div id="header">
            <h1>EAT A BROG</h1>
            <h2>Eat a bean</h2>

            <button @click="newBox">New Box</button>

            <select name="octaveSelector" id="octaveSelector" v-model.number="this.octaves">
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
            </select>
            <button @click="showPiano">Show Piano</button>


        </div>
        <div id="body">
            <SquareTile v-for="b in this.boxes" v-bind:key="b.number" v-bind:box="b" />

            <div v-if="pianoVisible" class="pianowrapper">
                <div class="piano" v-for="o in this.octaves" v-bind:key="o.value">
                    <PianoKey v-for="(key, index) in keyboardLayout" :key="index" :note="key.note" :isWhite="key.isWhite" />
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import SquareTile from './SquareTile.vue'
import PianoKey from ".//PianoKey.vue";

export default {
    name: "main-div",
    components: {
        SquareTile,
        PianoKey
    },
    props: {

    },
    data() {
        return {
            number: 0,
            octaves: 1,
            boxes: [],
            pianoVisible: false,
            keyboardLayout: [
                { note: "C", isWhite: true },
                { note: "C#", isWhite: false },
                { note: "D", isWhite: true },
                { note: "D#", isWhite: false },
                { note: "E", isWhite: true },
                { note: "F", isWhite: true },
                { note: "F#", isWhite: false },
                { note: "G", isWhite: true },
                { note: "G#", isWhite: false },
                { note: "A", isWhite: true },
                { note: "A#", isWhite: false },
                { note: "B", isWhite: true },

                // ...
            ],
        };
    },
    computed: {

    },
    methods: {
        newBox() {
            this.number++;
            this.boxes.push({ number: this.number });
            console.log("NEW BOX ", this.number)
        },
        showPiano() {
            this.pianoVisible = !this.pianoVisible;
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
    justify-content: center;
    padding: 10px;
}

h1 {
    margin: 0;
}

.piano,
.pianowrapper {
    display: flex;
}
</style>