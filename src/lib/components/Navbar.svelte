<script lang="ts">
  import { page } from '$app/stores';

  let menuOpen = false;

  const links = [
    { href: '/', label: 'Home' },
    { href: '/services', label: 'Services' },
    { href: '/about', label: 'About' },
    { href: '/contact', label: 'Contact' }
  ];

  const isActive = (href: string) => {
    const path = $page.url.pathname;
    return href === '/' ? path === href : path.startsWith(href);
  };

  const closeMenu = () => {
    menuOpen = false;
  };

  const handleResize = () => {
    if (window.innerWidth >= 768) {
      closeMenu();
    }
  };
</script>

<svelte:window on:resize={handleResize} />

<nav class="navbar">
  <div class="container navbar__inner">
    <a class="brand" href="/" aria-label="ASIS Business Ecigroup home" on:click={closeMenu}>
      <span class="brand__mark">AB</span>
      <span class="brand__text">ASIS Business Ecigroup</span>
    </a>

    <button
      class="menu-toggle"
      type="button"
      aria-label={menuOpen ? 'Close navigation menu' : 'Open navigation menu'}
      aria-expanded={menuOpen}
      on:click={() => (menuOpen = !menuOpen)}
    >
      <span></span>
      <span></span>
      <span></span>
    </button>

    <div class:menu-open={menuOpen} class="nav-links">
      {#each links as link}
        <a
          href={link.href}
          class:active={isActive(link.href)}
          on:click={closeMenu}
        >
          {link.label}
        </a>
      {/each}
      <a href="/contact" class="button button--small" on:click={closeMenu}>Let's Talk</a>
    </div>
  </div>
</nav>
