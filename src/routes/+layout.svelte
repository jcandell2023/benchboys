<script lang="ts">
    import '../app.scss'

    let active = false

    function toggleBurger(event:MouseEvent){
      event.preventDefault()
      active = !active
    }
</script>

<nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
        <a class="navbar-item" href="/">Bench Boys</a>
        <a
            role="button"
            class="navbar-burger {active && 'is-active'}"
            aria-label="menu"
            aria-expanded={active}
            data-target="navbarItems"
            on:click={toggleBurger}
        >
            <span aria-hidden="true" />
            <span aria-hidden="true" />
            <span aria-hidden="true" />
        </a>
    </div>
    <div id="navbarItems" class="navbar-menu {active && 'is-active'}">
        <div class="navbar-start">
            <a class="navbar-item" href="/"> Home </a>
            <a class="navbar-item" href="/articles"> Articles </a>
            <a class='navbar-item' href='/about'>About Us</a>
        </div>
    </div>
</nav>

<div class="container">
    <slot />
</div>
