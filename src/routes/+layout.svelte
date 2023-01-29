<script>
    import Toolbar from "$lib/Toolbar.svelte"
    import Sidebar from "$lib/Sidebar.svelte";
    import baseCSS from "$lib/Base.css?url";
	import StatusBar from "$lib/StatusBar.svelte";
</script>
<svelte:head>
    <link rel="stylesheet" href="{ baseCSS } " />
</svelte:head>

<!-- Create Grid layout -->
<div id="container">
    <Toolbar />
    <div id="content-row">
        <Sidebar />
        <div id="content-cell">
            <slot></slot>
        </div>
    </div>
    <StatusBar />
</div>

<style>
    #container {
        height: 100vh;
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: 1.5em 1fr 1.5em;
    }

    #content-row {
        width: 100%;
        display: grid;
        grid-template-columns: 250px 1fr;
        grid-template-rows: 1fr;
    }
</style>
