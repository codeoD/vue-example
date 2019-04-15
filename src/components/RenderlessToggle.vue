<template>
    <div>
        <toggle v-slot="{on, setOn, setOff, toggle}">
            <div class="button-group">
                <div :class="`button ${on ? 'btn-on' : 'btn-off'}`" @click="setOn"><span>On Action</span></div>
                <div :class="`button ${!on ? 'btn-on' : 'btn-off'}`" @click="setOff"><span>Off Action</span></div>
                <div class="button green" @click="toggle"><span>Toggle Action</span></div>
            </div>
        </toggle>
    </div>
</template>
<script>
const Toggle = {
    props: {
        on: {
            type: Boolean,
            default: false,
        }
    },
    data () {
        return {
            currentState: this.on
        }
    },
    methods: {
        setOn: function () {
            this.currentState = true
        },
        setOff: function () {
            this.currentState = false
        },
        toggle: function () {
            this.currentState = !this.currentState
        }
    },
    render(h) {
        return this.$scopedSlots.default({
            on: this.currentState,
            setOn: this.setOn,
            setOff: this.setOff,
            toggle: this.toggle,
        })
    },
}
export default {
    components: {
        Toggle,
    },
}
</script>
<style lang="scss" scoped>
.button {
    display: inline-block;
}
.btn-on {
    color: #fff;
    background-color: chartreuse;
}
.btn-off {
    color: #fff;
    background-color: cadetblue;
}
.green {
    color: green;
}
</style>
