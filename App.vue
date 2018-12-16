<script>
	export default {
		onLaunch: function () {
			console.log('App Launch')
		},
		onShow: function () {
			console.log('App Show')
		},
		onHide: function () {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	html{
		font-size: 16px;
	}
	uni-button:after{
		display: none;
	}
	uni-input div div{
		font-size: .8em;
	}
	uni-input div{
		width:100%;
	}
</style>
