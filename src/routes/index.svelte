<script context="module">
    export async function load({ fetch }) {
        let article;

        try {
        // here we fetch a single article
            article = await fetch(`https://api.francois-vidit.fr/posts/ja/iehamotomoto`);
            article = await article.json();
        } catch (e) {
            console.log(e);
        }
        return {
            props: {
                article
            }
        };
    }
</script>

<script>
    export let article;
</script>

<div>
    <pre>{JSON.stringify(article, null, 2)}</pre>
</div>