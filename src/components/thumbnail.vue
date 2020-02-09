<template lang="html">

	<a target="_blank" :href="image" @mouseover="isVisible(true)" @mouseleave="isVisible(false)">
		<img class="thumbnail" :src="image" :alt="alttext" :style="sizing"/>
	</a>

</template>

<script lang="js">

	export default {
		name: 'thumbnail',
		props: {
			image: {
				type: String,
				required: true
			},
			alttext: {
				type: String,
				required: true
			},
			width: {
				type: String,
				required: true
			},
			height: {
				type: String,
				required: true
			}
		},
		mounted () {

		},
		data () {
			return {
				isHover: false
			}
		},
		methods: {
			isVisible(status) {
				this.isHover = status;
			}
		},
		computed: {
			sizing: function(){
				return {
					width: this.width + "px",
					height: this.height + "px",
				}
			}
		}
	}


</script>

<style scoped lang="css">
	.thumbnail {
		border: 0.5px solid #ddd;
		transition: all 1s ease-in-out;
	}
</style>
