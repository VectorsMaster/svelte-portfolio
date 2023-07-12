<script>
	import { base } from '$app/paths';
</script>

<header class="header">
	<a href="{base}/" class="my-name">Ahmad Sarhan</a>
	<a href="{base}/comic/" class="get-a-joke">Get a joke!</a>
	<nav class="navbar">
		<a href="{base}/#home-section" class="active">Home</a>
		<a href="{base}/#contact-section" class="active">Contacts</a>
	</nav>
</header>

<style>
	.header {
		position: sticky;
		top: 0;
		left: 0;
		width: 100%;
		padding: 20px 10%;
		background-color: rgba(5, 139, 135, 0.978);
		display: flex;
		justify-content: space-between;
		align-items: center;
		z-index: 100;
	}

	.my-name {
		text-decoration: none;
		font-size: 25px;
		font-weight: 600;
		color: #ededed;
	}

	.get-a-joke {
		text-decoration: none;
		font-size: 50px;
		font-weight: 600;
		color: #ededed;
		transition: 0.3s;
		font-family: 'Brush Script MT', cursive;
	}

	.get-a-joke:hover {
		color: rgba(43, 238, 232, 0.978);
	}

	.navbar a {
		text-decoration: none;
		font-size: 18px;
		color: #ededed;
		font-weight: 500;
		margin-left: 35px;
		transition: 0.3s;
	}

	.navbar a:hover {
		color: rgba(43, 238, 232, 0.978);
	}
</style>
