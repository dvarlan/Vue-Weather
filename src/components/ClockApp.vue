<template>
    <div class="blur">
        <div class="clock">
            {{ this.time.hours }}:{{ this.time.minutes }}:{{ this.time.seconds }}
        </div>
        <div class="date">
            {{ this.date.day }}.{{ this.date.month }}.{{ this.date.year }}
        </div>
    </div>
</template>

<style scoped>
.clock {
    font-size: 90px;
    /*background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    backdrop-filter: blur(0.4px);
    border-radius: 10%;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
    width: max-content;
    margin: auto;*/
    color: rgba(181, 215, 246, 0.597);
}
.date {
    font-size: 50px;
    /*background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    backdrop-filter: blur(0.4px);
    border-radius: 10%;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
    width: max-content;
    margin: auto;*/
    color: rgba(181, 215, 246, 0.597);
}
.blur {
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    backdrop-filter: blur(0.4px);
    border-radius: 5%;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
    width: max-content;
    margin: auto;
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
            },
            date : {
                day: this.checkZero(currentDate.getDate()),
                month: this.checkZero(currentDate.getMonth() + 1),
                year: this.checkZero(currentDate.getFullYear())
            }
        }
    }, methods: {
        run () {
            currentDate = new Date()
            this.time.hours = this.checkZero(currentDate.getHours())
            this.time.minutes = this.checkZero(currentDate.getMinutes())
            this.time.seconds = this.checkZero(currentDate.getSeconds())
            this.date.day = this.checkZero(currentDate.getDate())
            this.date.month = this.checkZero(currentDate.getMonth() + 1)
            this.date.year = this.checkZero(currentDate.getFullYear())
        },
        checkZero (value) {
            // Adds leading 0s to value
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