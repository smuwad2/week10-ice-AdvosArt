<script>
    export default { 
        data() {
            return {
                soundEmojis: ['🔇', '🔈', '🔉', '🔊']
            }
        },
        // TODO: add code to define a necessary prop
        props: [
            "soundLvl"
        ]
    }
</script>

<template>
    <!-- TODO: add your template code here. Use span element. --> 
    <span>{{ soundEmojis[Number(soundLvl)] }}</span>
</template>