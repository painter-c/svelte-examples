<script>
    import BlockText from "../lib/BlockText/BlockText.svelte";

    let exampleText = "They call me the Hunter, And now that I'm here, your part in glimpsing the Unity is over."
    let examplePrefix = "The Hunter:"
</script>

<div class="background">
 <BlockText text={exampleText} prefix={examplePrefix} width={76}/>
</div>

<svelte:head>
    <link rel="stylesheet" href="./src/lib/base.css">
</svelte:head>

<style>
    .background {
        position: fixed;
        box-sizing: border-box;
        left: 0;
        right: 0;
        width: 100%;
        height: 100%;
        padding: 1rem;
        
        background: radial-gradient(ellipse 80% 80% at bottom in hsl, rgb(29, 41, 68) 0%, rgb(23, 32, 53) 100%);

        color: rgba(255, 255, 255, 0.9);
        font-size: 1rem;
    }
</style>