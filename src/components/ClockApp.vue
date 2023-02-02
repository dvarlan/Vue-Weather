<template>
    <div class="clock">
    {{ time.hours }}:{{ time.minutes }}:{{ time.seconds }}
    </div>
</template>

<style scoped>
.clock {
    font-size: 90px;
}
</style>

<script>
const currentDate = new Date()

export default {
    data () {
        return {
            time : {
                hours: currentDate.getHours(),
                minutes: currentDate.getMinutes(),
                seconds: currentDate.getSeconds()
            }
        }
    }
}
</script>