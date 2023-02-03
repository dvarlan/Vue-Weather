<template>
    <div class="clock">
    {{ this.time.hours }}:{{ this.time.minutes }}:{{ this.time.seconds }}
    </div>
</template>

<style scoped>
.clock {
    font-size: 90px;
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    backdrop-filter: blur(0.4px);
    border-radius: 10%;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
    width: max-content;
    margin: auto;
    color: rgba(181, 215, 246, 0.597);
}
</style>

<script>
let currentDate = new Date()

export default {
    data () {
        return {
            time : {
                hours: this.checkZero(currentDate.getHours()),
                minutes: this.checkZero(currentDate.getMinutes()),
                seconds: this.checkZero(currentDate.getSeconds())
            }
        }
    }, methods: {
        run () {
            currentDate = new Date()
            this.time.hours = this.checkZero(currentDate.getHours())
            this.time.minutes = this.checkZero(currentDate.getMinutes())
            this.time.seconds = this.checkZero(currentDate.getSeconds())
        },
        checkZero (value) {
            // Displays 19h 1min 2sec as 19:01:02 instead of 19:1:2
            if (value < 10) {
                return "0" + value
            } else {
                return value
            }
        }
    },
    mounted () {
        setInterval(this.run, 1000)
    }
}
</script>