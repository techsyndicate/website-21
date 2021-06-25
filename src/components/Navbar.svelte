<script>
    import { Link } from 'svelte-navigator'
    let activePath = window.location.pathname

    window.onload = () => {
        const screenWidth = screen.width
        if(screenWidth < 768) {
            document.getElementById('normal-nav').style.display = "none"
            document.getElementById('responsive-nav').style.display = "flex"
            hideSidebar()
        } else {
            document.getElementById('normal-nav').style.display = "flex"
            document.getElementById('responsive-nav').style.display = "none"
        }
    }

    window.addEventListener("resize", () => {
        const screenWidth = screen.width
        if (screenWidth < 768) {
            document.getElementById('normal-nav').style.display = "none"
            document.getElementById('responsive-nav').style.display = "flex"
        } else {
            document.getElementById('normal-nav').style.display = "flex"
            document.getElementById('responsive-nav').style.display = "none"
        }
    })

    window.addEventListener('click', (e) => {
        activePath = window.location.pathname
        if(e.target.id === "hamburger-icon") { showSidebar() }
        else if(e.target.id === "close-icon") { hideSidebar() }
        else if(e.target.id === "sidebar-link" || e.target.id === "ts-sidebar") { hideSidebar() }
    })

    const showSidebar = () => {
        try {
            document.getElementsByClassName('sidebar')[0].style.display = "block"
            document.getElementsByTagName('html')[0].style.overflow = "hidden"
        } catch (err) { console.log(err) }
    }

    const hideSidebar = () => {
        try {
            document.getElementsByClassName('sidebar')[0].style.display = "none"
            document.getElementsByTagName('html')[0].style.overflow = "initial"
        } catch (err) { console.log(err) }
    }
</script>

<style>
    nav {
        padding-left: 5vw;
        padding-right: 5vw;
        padding-top: 2vh;
        padding-bottom: 2vh;
        background-color:transparent;
        width: 90vw;
        height: 5.5vh;
        display: flex;
        flex-flow: row wrap;
        align-items: center;
    }

    nav img {
        width: 3vw;
        height: 3vw;
        /* margin-top: -0.5vh; */
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

    .sidebar {
        background-color: #111;
        width: 100vw;
        height: 200vw;
        z-index: 9999999;
        overflow: hidden;
        overflow-y: hidden;
        position: fixed;
    }

    .sidebar img {
        position: absolute;
        right: 0;
        margin-right: 10.5vw;
        width: 4.5vw;
        height: 4.5vw;
        margin-top: 8vw;
    }

    .sidebar .links {
        height: 100%;
        width: 40vw;
        margin: auto;
        text-align: center;
        padding-top: 32vh;
    }

    #ts-sidebar {
        width: 18vw;
        height: 18vw;
        margin-right: 42.5%;
        margin-top: -20vw;
    }

    .sidebar-nav-link {
        font-size: 5vw;
        margin-top: 7vw;
        color: white;
    }

    .sidebar-nav-link-button {
        border:none;
        background-color: #00AF3B;
        color: white;
        border-radius: 5px;
        font-size: 5vw;
        padding: 1vh 3vw;
        margin-top: 3vw;
        margin-left: 3vw;
    }

    .sidebar-nav-link-active {
        color: #16e16e;
    }

    @media screen and (max-width: 768px) {
        nav img {
            width: 10vw;
            height: 10vw;
            margin-top: 3vw;
            margin-right: 3vw;
            /* margin-top: -0.5vh; */
        }

        #ts {
            width: 12vw;
            height: 12vw;
            margin-top: 0.5vw;
        }
    }
</style>

<body>
    <nav style="display: none;" id="normal-nav">
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
    <div class="sidebar" style="display: none;">
        <img src="/assets/icons/close.svg" alt="close" id="close-icon">
        <div class="links">
            <Link to="/"><img src="/assets/images/ts.png" alt="ts" id="ts-sidebar"></Link>
            {#if activePath === '/events'}
                <Link to="/events" style="text-decoration: none;"><p class="sidebar-nav-link sidebar-nav-link-active" id="sidebar-link">Events</p></Link>
            {:else}
                <Link to="/events" style="text-decoration: none;"><p class="sidebar-nav-link" id="sidebar-link">Events</p></Link>
            {/if}
            {#if activePath === '/members'}
                <Link to="/members" style="text-decoration: none;"><p class="sidebar-nav-link sidebar-nav-link-active" id="sidebar-link">Members</p></Link>
            {:else}
                <Link to="/members" style="text-decoration: none;"><p class="sidebar-nav-link" id="sidebar-link">Members</p></Link>
            {/if}
            {#if activePath === '/alumni'}
                <Link to="/alumni" style="text-decoration: none;"><p class="sidebar-nav-link sidebar-nav-link-active" id="sidebar-link">Alumni</p></Link>
            {:else}
                <Link to="/alumni" style="text-decoration: none;"><p class="sidebar-nav-link" id="sidebar-link">Alumni</p></Link>
            {/if}
            {#if activePath === '/learn'}
                <Link to="/learn" style="text-decoration: none;"><p class="sidebar-nav-link sidebar-nav-link-active" id="sidebar-link">Learn</p></Link>
            {:else}
                <Link to="/learn" style="text-decoration: none;"><p class="sidebar-nav-link" id="sidebar-link">Learn</p></Link>
            {/if}
            <Link to="/register" style="text-decoration: none;"><button class="sidebar-nav-link-button" id="sidebar-link">Register</button></Link>
        </div>
    </div>
    <nav style="display: none;" id="responsive-nav">
        <div class="left">
            {#if activePath !== '/'}
                <Link to="/"><img src="/assets/images/ts.png" alt="ts" id="ts"></Link>
            {/if}
        </div>
        <div class="right">
            <img src="/assets/icons/hamburger.svg" alt="hamburger-icon" id="hamburger-icon">
        </div>
    </nav>
</body>