<template>
    <div :class="['piano-key', isWhite ? 'white-key' : 'black-key', isActive && 'active']" @mousedown="playNote"
        @mouseup="stopNote" @touchstart="playNote" @touchend="stopNote">
        <div class="note-label">{{ note }}</div>
    </div>
</template>

<script>
export default {
    props: {
        note: String,
        isWhite: Boolean,
    },
    data() {
        return {
            isActive: false,
        };
    },
    methods: {
        playNote() {
            this.isActive = true;
            // Use oscillator
        },
        stopNote() {
            this.isActive = false;
        },
    },
}
</script>

<style scoped>
.piano-key {
    height: 200px;
    width: 50px;
    border-radius: 0 0 3px 3px;
    box-shadow: 1px 2px gray;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    cursor: pointer;
}

.piano-key:hover {
    transform: scale(1.01);
}

.white-key {
    background-color: white;
    border: 1px solid black;
}

.black-key {
    background-color: black;
    height: 120px;
    width: 40px;
    margin: 0 -20px;
    z-index: 1;
}

.active {
    background-color: #ffcc00;
}
</style>