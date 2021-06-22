<script>
    import { Link } from 'svelte-navigator'
    let activePath = window.location.pathname
    window.addEventListener('click', () => {
        activePath = window.location.pathname
    })
</script>

<style>
    nav {
        position: absolute;
        top: 0;
        right: 0;
        left: 0;
        padding-left: 5vw;
        padding-right: 5vw;
        padding-top: 2vh;
        padding-bottom: 2vh;
        background-color: #030303;
        width: 90vw;
        height: 5.5vh;
        display: flex;
        flex-flow: row wrap;
        align-items: center;
    }

    nav img {
        width: 3vw;
        height: 3vw;
        margin-top: -0.5vh;
    }

    nav .right {
        position: absolute;
        right: 0;
        margin-right: 5vw;
        display: flex;
        flex-flow: row wrap;
        align-items: center;
    }

    .nav-link {
        font-size: 0.98vw;
        color: white;
        text-decoration: none;
        transition: all 0.3s;
        /* width: 10vw; */
        margin-left: 4vw;
        position: relative;
    }

    .nav-link::after {
        content: "";
        position: absolute;
        bottom: -2px;
        left: 0;
        width: 0;
        height: 2px;
        background: #16e16e;
        transition: all 0.2s;
    }

    .nav-link:hover:after {
        width: 100%;
    }

    .active:after {
        width: 100%;
    }

    .nav-link-button {
        text-decoration: none;
        border:none;
        background-color: #00AF3B;
        color: white;
        border-radius: 5px;
        font-size: 0.98vw;
        margin-left: 4vw;
        padding: 0.8vh 1.2vw;
        transition: all 0.2s;
    }
</style>

<body>
    <nav>
        <div class="left">
            <Link to="/"><img src="/assets/images/ts.png" alt="ts"></Link>
        </div>
        <div class="right">
            {#if activePath === '/events'}
                <Link to="/events" style="text-decoration: none;"><span class="nav-link active">Events</span></Link>
            {:else}
                <Link to="/events" style="text-decoration: none;"><span class="nav-link">Events</span></Link>
            {/if}
            {#if activePath === '/members'}
                <Link to="/members" style="text-decoration: none;"><span class="nav-link active">Members</span></Link>
            {:else}
                <Link to="/members" style="text-decoration: none;"><span class="nav-link">Members</span></Link>
            {/if}
            {#if activePath === '/alumni'}
                <Link to="/alumni" style="text-decoration: none;"><span class="nav-link active">Alumni</span></Link>
            {:else}
                <Link to="/alumni" style="text-decoration: none;"><span class="nav-link">Alumni</span></Link>
            {/if}
            {#if activePath === '/learn'}
                <Link to="/learn" style="text-decoration: none;"><span class="nav-link active">Learn</span></Link>
            {:else}
                <Link to="/learn" style="text-decoration: none;"><span class="nav-link">Learn</span></Link>
            {/if}
            <Link to="/register" style="text-decoration: none;"><span class="nav-link-button">Register</span></Link>
        </div>
    </nav>
</body>