<!-- option -->
<script>
export default {
    data() {
        return {
            name: "John Doe",
            status: "active",
            tasks: [
                "task1", "task2", "task3", "task4"
            ],
            link: "https://www.google.com"
        }
    },
    methods: {
        toggleStatus() {
            if (this.status === 'active') {
                this.status = 'pending';
            } else if (this.status === 'pending') {
                this.status = 'inactive';
            } else {
                this.status = 'active'
            }
        }
    }
}
</script>

<template>
    <h1>hello {{ name }}</h1>

    <!-- v-if : will render when value of v-if = true -->
    <p v-if="status === 'active'">User is active</p>
    <p v-else-if="status === 'pending'">User is pending</p>
    <p v-else>Inactivate User</p>

    <h3>Tasks: </h3>
    <ul>
        <li v-for="task in tasks" :key="task"> {{ task }}</li>
    </ul>

    <!-- <a v-bind:href="link">Click for google</a> -->
    <a :href="link">Click for google</a>
    <br />
    <!-- <button v-on:click="toggleStatus">Change Status</button> -->
    <button @click="toggleStatus">Change Status</button>

</template>
<style scoped>
h1 {
    color: red;
}
</style>
