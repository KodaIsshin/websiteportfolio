<script lang="ts">
    import {Router, type RouteConfig} from "@mateothegreat/svelte5-router";
    import home from "./home.svelte";
    import portfolio from "./routes/portfolio.svelte";
    

    const routes: RouteConfig[] = [
        {
            path: "",
            component: home
        },
        {
            path: "/portfolio",
            component: portfolio
        }
    ]

</script>

<Router {routes}/>