<template>
    <div>
        <input type="text">
		<ul v-for="toilet in toilets" v-bind:key="toilet._id">
			<li>{{ toilet._id }}</li>
		</ul>
    </div>
</template>

<script>
export default {
	name: 'Search',
    pouch: {
        toilets() {
            return {
                selector: { }
            }
        }
    },
}
</script>

<style>
</style>
