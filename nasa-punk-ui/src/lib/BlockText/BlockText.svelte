<script>
    export let prefix = null
    export let text = 'no text'
    export let width = 80;

    let prefixOr = () => {
        if (prefix) return `${prefix} `
        return ''
    }

    let lines = () => {
        let start = 0
        let end = start + parseInt(width)
        let result = []

        while (start < text.length) {
            let fallback = Math.max(end - 10, 0)
            while (text.at(end) !== ' ' && end > fallback) {
                end -= 1
            }
            result.push(text.substring(start, end))
            start = end
            end = end + width
        }

        return result
    }
</script>

<div class='container'>
    {#each lines() as line, i}
        <p class='block-text'>
            {#if i === 0}
                <span class='prefix'>{prefixOr()}</span>
            {/if}
            {line}
        </p><br>
    {/each}
</div>

<style>
    .container {
        text-align: center;
        width: max-content;
    }
    .block-text {
        display: inline-block;
        background-color: black;
        margin: 0 0 3px 0;
        padding: 4px 8px 4px 8px;
        opacity: 80%;
    }
    .prefix {
        color: rgb(233, 230, 205);
    }
</style>