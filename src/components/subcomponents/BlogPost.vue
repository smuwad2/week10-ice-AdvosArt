<script>
    export default {
        // Add code if/as necessary
        // Hint: Add properties subject, entry and mood
        props: [
            "subject",
            "entry",
            "mood"
        ],
        methods: {
            imageLink(name) {
                return "/assets/" + name.toLowerCase() + ".png";
            }
        }
    }
</script>


<template>
    <!-- TODO: add your template code here. Use boostrap card --> 
    <div class="card">
        <img v-bind:src="imageLink(mood)" class="card-img-top" v-bind:alt="mood">
        <div class="card-body">
            <h5 class="card-title">{{ subject }}</h5>
            <p class="card-text">{{ entry }}</p>
        </div>
    </div>
</template>

