<template>
	<div class="is-scrollable">
		<div class="page-home">
			<div class="home-connect">
				<connect @update:query="val => this.urlArgs = val" />
			</div>
		</div>
	</div>
</template>

<script>
	import Connect from '../connect'

	export default {
		components: {
			Connect
		},
		data() {
			return {
				urlArgs: ''
			}
		},
		computed: {
			exampleURL() {
				return `${location.origin + location.pathname}#!auto${this.urlArgs}`
			},
			httpURL() {
				return location.href.replace('https://', 'http://')
			},
			showHTTPSWarning() {
				return location.protocol === 'https:'
			}
		},
		methods: {
			selectValue(e) {
				e.target.select()
			}
		}
	}
</script>
