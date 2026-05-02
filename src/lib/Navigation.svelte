<script lang="ts">
    let innerWidth: number

    import {page} from '$app/state';

    const pages = [
        { name: 'home', path: '/'},
        {name: 'about me', path: '/about'},
        {name:'my games', path:'/games'},
    ]
</script>

<svelte:window bind:innerWidth={innerWidth} />

<nav id="navbar">
    <span id="title">amethyst.gay</span>
    <ul>
        {#each pages as item}
            <li>
                <a href="{item.path}">
                    <img src="/assets/nav_heart_{page.url.pathname === item.path ? 'full' : 'empty'}.png">
                    <span>{item.name}</span>
                </a>
            </li>
        {/each}

    </ul>
</nav>

<style lang="scss">
    #navbar {
      font-family: var(--font-pixel);
      padding: 0.2rem 0.5rem;
      border: 4px solid #FF56D9;
      font-size: 1.2rem;
      color: #FFAADA;
      background: rgba(121, 57, 228, 0.5);
      display: flex;
      gap: 1rem;
      flex-direction: column;
      list-style: none;

      #title {
        text-decoration: underline;
        text-decoration-thickness: 3px;
        text-underline-offset: 8px;
        text-decoration-style: dashed;

      }

      li:hover a span {
        text-decoration: underline;
        text-decoration-thickness: 2px;
        text-decoration-color: #FF89D5;
        text-underline-offset: 4px;
      }

      li a {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        text-decoration: none;
        color: inherit;

        img {
          width: 1.5rem;
        }
      }
    }
</style>