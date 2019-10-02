<template>
    <div>
        <input v-model="toiletKey" placeholder="Burgerking Hauptbahnhof Zürich" type="text">
        <input v-model="toiletCode" placeholder="6392" type="text">
        <button @click="addToilett">leak</button>
    </div>
</template>

<script>
import uniqid from 'uniqid'

export default {
	name: 'Add',
    data() {
        return {
            newId: uniqid(),
            toiletKey: null,
            toiletCode: null
        }
    },
    methods: {
        addToilett() {
        	this.$pouch.put({
                _id: this.newId,
                toiletKey: this.toiletKey,
                toiletCode: this.toiletCode
            }).then(() => {})
            
            this.newId = uniqid()
            this.toiletKey = null
            this.toiletCode = null
        }
    }
}
</script>

<style>
</style>
