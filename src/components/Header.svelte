<script>
    import FaHamburger from 'svelte-icons/fa/FaHamburger.svelte'
    let closed = true
    const handleClick = () => {
        closed == true ? closed = false : closed = true
    }
    //  <!-- <Icon class="icon" pack="charm" name="menu-hamburger"/></button> -->
</script>

<header class={closed && "closed"}>
    <div class="logo">
        <button on:click={handleClick} class="hamburger">
            <FaHamburger />
         </button>
         <a class="link" href="/blog">Broken Coder</a>
    </div>
    
    <nav>
        <a class="link" id="home" href="/">Home</a>
        <a class="link" id="blog" href="/blog">Blog</a>
        <a class="link" id="about" href="/about">About</a>
        <a class="link" id="support" href="/support">Support Me</a>
    </nav>
</header>

<style>
    .hamburger {
        height: 3rem;
        width: 3rem;
        color: var(--text-dark);
    }
    /* Header Link Styles */

    a {
        text-decoration: none;
        color: var(--text-white);
        font-size: 2rem;
    }
    a:hover {
        color: var(--text-white);
    }
    nav a {
        color: var(--text-muted);
    }
    .closed nav a {
        display: none;
    }
    @media screen and (min-width: 700px) {
        header {
            height: 100vh;
        }
        .hamburger {
            display: none;
        }
        .closed nav a {
            display: block;
        }
        .logo {
            margin-bottom: 2em;
        }
        
    }
</style>