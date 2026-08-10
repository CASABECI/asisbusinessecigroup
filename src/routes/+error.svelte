<script lang="ts">
  import { page } from '$app/stores';

  $: status = $page.status;
  $: message = $page.error?.message ?? 'The page you requested could not be found.';
</script>

<svelte:head>
  <title>Error | ASIS Business Ecigroup</title>
  <meta
    name="description"
    content="ASIS Business Ecigroup page not found or unavailable. Return to the homepage or contact us for assistance."
  />
</svelte:head>

<section class="section error-section">
  <div class="container error-card card">
    <span class="eyebrow">Something went wrong</span>
    <h1>{status}</h1>
    <h2>{status === 404 ? 'Page not found' : 'We could not complete your request'}</h2>
    <p>{message}</p>
    <div class="error-actions">
      <a class="button" href="/">Back to Home</a>
      <a class="button button--secondary-dark" href="/contact">Contact Support</a>
    </div>
  </div>
</section>

<style>
  .error-section {
    display: grid;
    place-items: center;
    min-height: 70vh;
  }

  .error-card {
    max-width: 720px;
    text-align: center;
    margin: 0 auto;
  }

  .error-card h1 {
    margin: 0;
    font-size: clamp(4rem, 10vw, 6rem);
    color: var(--color-primary);
    line-height: 1;
  }

  .error-actions {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-top: 2rem;
    align-items: center;
  }

  @media (min-width: 768px) {
    .error-actions {
      flex-direction: row;
      justify-content: center;
    }
  }
</style>
