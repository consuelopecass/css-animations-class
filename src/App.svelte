<script>
    import { Router, Link, Route } from "svelte-routing";
    import Home from './views/home.svelte';

    let url = '';
</script>

<Router url="{url}">
    <nav>
        <Link to="/">Home</Link>
    </nav>
    <div class="routes">
        <Route path="/">
            <Home />
        </Route>
    </div>
</Router>

<style>
    :global(body) {
        position: relative;
        display: flex;
        flex-direction: column;
        background: #222;
        color: #ededed;
    }

    nav {
        display: flex;
        padding: 8px;
        background: #333;
    }

    nav :global(a) {
        display: block;
        padding: .25em .5em;
        margin: 0 .25em;
        background: hsl(40 100% 50% / 1);
        color: #222;
        border-radius: 2px;
        text-decoration: none;
        transition: all 250ms ease;
    }

    nav :global(a[aria-current]) {
        background: hsl(55 100% 50% / 1);
    }

    nav :global(a:hover) {
        color: #000;
        background: hsl(40 100% 40% / 1);
        border-radius: 1em;
    }

    .routes {
        display: flex;
        flex: 1;
        padding: 8px;
    }
</style>
