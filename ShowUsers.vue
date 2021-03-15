<template>
    <div>
    <div v-if="isActive">
        <p>TEST</p>
        <p v-text="this.count"></p>
        <p v-for="user in users" :key="user">
            {{user}}
        </p>
    </div>
    <button @click="toggleStatus">Toggle Active Status</button>
    </div>
</template>

<script>
export default {
    name: 'ShowUsers',
    props: {
        status: {
            type: String,
            required: false
        },
        users: {
            type: Array,
            required: false,
            default() {
                return [
            'First',
            'Second',
            'Last'
            ]
            }
        },
    },
    data () {
        return {
            count: 1,
            isActive: true
        }
    },
    methods: {
        toggleStatus () {
            this.isActive = !this.isActive;
        }
    }
}
</script>

<style scoped>
    p {
        color: red;
        font-size: 2rem;
    }
</style>
