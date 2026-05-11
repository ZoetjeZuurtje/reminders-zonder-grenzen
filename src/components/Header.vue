        <script setup lang="ts">
        </script>

<template>
	<header id="site-header">
        <!-- <img src='./../../public/kraken.jpg' alt="Kraken" width="100"> -->
		<div class="container">
			<h1>Reminders zonder Grenzen</h1>
			<p class="tagline">We know where to find you</p>
		</div>
        <a href="https://steun.artsenzondergrenzen.nl/doe-een-gift">Support us</a>
	</header>
</template>


<style scoped>
#site-header {
	padding: 20px;
	border-bottom: 1px solid var(--border);
    .container {
        text-align: left;
    }
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.tagline {
	margin-top: 6px;
	color: var(--text);
}
a {
    background-color: var(--accent-bg);
    color: var(--accent);
    :hover {
        border: solid 2px var(--accent-border);
    }
    padding: 10px;
    border-radius: 10px;
    height: min-content;
}
</style>
