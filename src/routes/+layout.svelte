<script lang="ts">
  import Navbar from '$lib/components/Navbar.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
  <meta name="theme-color" content="#1e3a5f" />
  <meta name="author" content="ASIS Business Ecigroup" />
  <meta name="robots" content="index, follow" />
</svelte:head>

<div class="site-shell">
  <Navbar />
  <main>
    <slot />
  </main>
  <Footer />
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap');

  :global(:root) {
    --color-primary: #1e3a5f;
    --color-secondary: #2d6a9f;
    --color-accent: #f0a500;
    --color-light: #f8f9fa;
    --color-dark: #212529;
    --color-muted: #5f6b7a;
    --color-white: #ffffff;
    --shadow-soft: 0 18px 50px rgba(30, 58, 95, 0.12);
    --shadow-card: 0 12px 30px rgba(30, 58, 95, 0.08);
    --border-radius: 1rem;
    --container-width: 1180px;
    --transition: all 0.3s ease;
  }

  :global(html) {
    scroll-behavior: smooth;
  }

  :global(body) {
    margin: 0;
    font-family: 'Inter', system-ui, sans-serif;
    color: var(--color-dark);
    background: var(--color-light);
    line-height: 1.6;
  }

  :global(*),
  :global(*::before),
  :global(*::after) {
    box-sizing: border-box;
  }

  :global(a) {
    color: inherit;
    text-decoration: none;
    transition: var(--transition);
  }

  :global(img) {
    max-width: 100%;
    display: block;
  }

  :global(button),
  :global(input),
  :global(textarea) {
    font: inherit;
  }

  :global(main) {
    min-height: 60vh;
  }

  .site-shell {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }

  :global(.container) {
    width: min(calc(100% - 2rem), var(--container-width));
    margin: 0 auto;
  }

  :global(.section) {
    padding: 4rem 0;
  }

  :global(.section--tight) {
    padding: 3rem 0;
  }

  :global(.section-title) {
    margin: 0 0 1rem;
    font-size: clamp(2rem, 4vw, 3rem);
    line-height: 1.1;
    color: var(--color-primary);
  }

  :global(.section-subtitle) {
    max-width: 760px;
    margin: 0 auto 2rem;
    color: var(--color-muted);
    font-size: 1.05rem;
  }

  :global(.eyebrow) {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--color-accent);
    margin-bottom: 1rem;
  }

  :global(.eyebrow::before) {
    content: '';
    width: 2rem;
    height: 2px;
    background: currentColor;
  }

  :global(.button) {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    padding: 0.9rem 1.5rem;
    border-radius: 999px;
    border: 2px solid transparent;
    background: var(--color-accent);
    color: var(--color-primary);
    font-weight: 700;
    transition: var(--transition);
    cursor: pointer;
  }

  :global(.button:hover),
  :global(.button:focus-visible) {
    transform: translateY(-2px);
    box-shadow: var(--shadow-card);
  }

  :global(.button--secondary) {
    background: transparent;
    border-color: rgba(255, 255, 255, 0.35);
    color: var(--color-white);
  }

  :global(.button--secondary-dark) {
    background: transparent;
    border-color: rgba(30, 58, 95, 0.2);
    color: var(--color-primary);
  }

  :global(.button--small) {
    padding: 0.75rem 1.1rem;
    font-size: 0.95rem;
  }

  :global(.grid) {
    display: grid;
    gap: 1.5rem;
  }

  :global(.card) {
    background: var(--color-white);
    border-radius: var(--border-radius);
    padding: 1.75rem;
    box-shadow: var(--shadow-card);
    transition: var(--transition);
  }

  :global(.card:hover) {
    transform: translateY(-6px);
    box-shadow: var(--shadow-soft);
  }

  :global(.badge-icon) {
    width: 3rem;
    height: 3rem;
    border-radius: 0.9rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    background: rgba(45, 106, 159, 0.12);
    color: var(--color-secondary);
    font-size: 1.4rem;
    margin-bottom: 1rem;
  }

  :global(.page-hero) {
    padding: 7rem 0 3.5rem;
    background: linear-gradient(145deg, rgba(30, 58, 95, 0.98), rgba(45, 106, 159, 0.88));
    color: var(--color-white);
  }

  :global(.page-hero h1) {
    margin: 0 0 1rem;
    font-size: clamp(2.5rem, 5vw, 4.25rem);
    line-height: 1.05;
  }

  :global(.page-hero p) {
    max-width: 720px;
    margin: 0;
    color: rgba(255, 255, 255, 0.88);
    font-size: 1.1rem;
  }

  :global(.navbar) {
    position: sticky;
    top: 0;
    z-index: 50;
    background: rgba(248, 249, 250, 0.92);
    backdrop-filter: blur(18px);
    border-bottom: 1px solid rgba(30, 58, 95, 0.08);
  }

  :global(.navbar__inner) {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.95rem 0;
    gap: 1rem;
  }

  :global(.brand) {
    display: inline-flex;
    align-items: center;
    gap: 0.85rem;
    font-weight: 800;
    color: var(--color-primary);
  }

  :global(.brand__mark) {
    width: 2.75rem;
    height: 2.75rem;
    border-radius: 0.9rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    background: var(--color-primary);
    color: var(--color-white);
  }

  :global(.brand__text) {
    max-width: 11rem;
    line-height: 1.1;
  }

  :global(.menu-toggle) {
    display: inline-flex;
    flex-direction: column;
    justify-content: center;
    gap: 0.28rem;
    width: 3rem;
    height: 3rem;
    padding: 0.7rem;
    border: 0;
    border-radius: 0.8rem;
    background: rgba(30, 58, 95, 0.08);
    cursor: pointer;
  }

  :global(.menu-toggle span) {
    width: 100%;
    height: 2px;
    background: var(--color-primary);
    border-radius: 999px;
  }

  :global(.nav-links) {
    position: absolute;
    top: calc(100% + 0.75rem);
    left: 1rem;
    right: 1rem;
    display: none;
    flex-direction: column;
    align-items: stretch;
    gap: 0.8rem;
    padding: 1rem;
    background: var(--color-white);
    border-radius: 1rem;
    box-shadow: var(--shadow-soft);
  }

  :global(.nav-links.menu-open) {
    display: flex;
  }

  :global(.nav-links a) {
    color: var(--color-primary);
    font-weight: 600;
  }

  :global(.nav-links a.active) {
    color: var(--color-secondary);
  }

  :global(.site-footer) {
    margin-top: auto;
    background: var(--color-primary);
    color: rgba(255, 255, 255, 0.88);
  }

  :global(.footer-grid) {
    display: grid;
    gap: 2rem;
    padding: 3.5rem 0 2.5rem;
  }

  :global(.site-footer h2),
  :global(.site-footer h3) {
    margin-top: 0;
    color: var(--color-white);
  }

  :global(.site-footer ul) {
    list-style: none;
    padding: 0;
    margin: 0;
    display: grid;
    gap: 0.75rem;
  }

  :global(.site-footer a:hover) {
    color: var(--color-accent);
  }

  :global(.social-links) {
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  }

  :global(.footer-bottom) {
    border-top: 1px solid rgba(255, 255, 255, 0.12);
  }

  :global(.footer-bottom__inner) {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    padding: 1.1rem 0 1.5rem;
    font-size: 0.95rem;
  }

  :global(.stats-grid),
  :global(.feature-grid),
  :global(.service-grid),
  :global(.values-grid),
  :global(.team-grid),
  :global(.contact-grid),
  :global(.why-grid) {
    grid-template-columns: 1fr;
  }

  :global(.pill-list) {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    padding: 0;
    margin: 1.5rem 0 0;
    list-style: none;
  }

  :global(.pill-list li) {
    padding: 0.65rem 1rem;
    border-radius: 999px;
    background: rgba(45, 106, 159, 0.1);
    color: var(--color-primary);
    font-weight: 600;
  }

  :global(.form-group) {
    display: grid;
    gap: 0.45rem;
  }

  :global(label) {
    font-weight: 600;
    color: var(--color-primary);
  }

  :global(input),
  :global(textarea) {
    width: 100%;
    border: 1px solid rgba(30, 58, 95, 0.15);
    border-radius: 0.9rem;
    padding: 0.95rem 1rem;
    background: var(--color-white);
    color: var(--color-dark);
    transition: var(--transition);
  }

  :global(input:focus),
  :global(textarea:focus) {
    outline: none;
    border-color: var(--color-secondary);
    box-shadow: 0 0 0 4px rgba(45, 106, 159, 0.12);
  }

  :global(.error-text) {
    color: #b3261e;
    font-size: 0.92rem;
  }

  :global(.success-box),
  :global(.info-box) {
    border-radius: 1rem;
    padding: 1rem 1.1rem;
  }

  :global(.success-box) {
    background: rgba(51, 171, 90, 0.12);
    color: #1f6f3d;
  }

  :global(.info-box) {
    background: rgba(45, 106, 159, 0.08);
    color: var(--color-primary);
  }

  @media (min-width: 768px) {
    :global(.section) {
      padding: 5rem 0;
    }

    :global(.brand__text) {
      max-width: none;
    }

    :global(.menu-toggle) {
      display: none;
    }

    :global(.nav-links) {
      position: static;
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-end;
      gap: 1.25rem;
      padding: 0;
      background: transparent;
      box-shadow: none;
    }

    :global(.footer-grid),
    :global(.feature-grid),
    :global(.service-grid),
    :global(.values-grid),
    :global(.team-grid),
    :global(.contact-grid),
    :global(.why-grid) {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    :global(.stats-grid) {
      grid-template-columns: repeat(4, minmax(0, 1fr));
    }

    :global(.footer-bottom__inner) {
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
    }
  }

  @media (min-width: 1024px) {
    :global(.feature-grid) {
      grid-template-columns: repeat(4, minmax(0, 1fr));
    }

    :global(.service-grid) {
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }

    :global(.team-grid),
    :global(.values-grid) {
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }

    :global(.footer-grid) {
      grid-template-columns: 1.25fr 0.8fr 1fr 0.8fr;
    }

    :global(.contact-grid) {
      grid-template-columns: 1.15fr 0.85fr;
    }

    :global(.why-grid) {
      grid-template-columns: repeat(4, minmax(0, 1fr));
    }
  }
</style>
