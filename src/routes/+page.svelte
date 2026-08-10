<script lang="ts">
  let email = '';
  let newsletterMessage = '';
  let newsletterError = '';

  const handleNewsletterSubmit = () => {
    newsletterError = '';
    newsletterMessage = '';

    if (!email.trim()) {
      newsletterError = 'Please enter your email address to join our business insights newsletter.';
      return;
    }

    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
      newsletterError = 'Please provide a valid business email address.';
      return;
    }

    newsletterMessage = `Thank you for subscribing, ${email}. We'll share growth insights soon.`;
    email = '';
  };
</script>

<svelte:head>
  <title>ASIS Business Ecigroup | Business Growth & Excellence</title>
  <meta
    name="description"
    content="ASIS Business Ecigroup helps organizations improve operations, strengthen strategy, and accelerate sustainable growth through expert business services."
  />
  <link rel="canonical" href="https://asisbusinessecigroup.com/" />
  <meta property="og:title" content="ASIS Business Ecigroup" />
  <meta
    property="og:description"
    content="Your trusted business partner for growth, operational excellence, and strategic transformation."
  />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://asisbusinessecigroup.com/" />
</svelte:head>

<section class="page-hero">
  <div class="container hero-grid">
    <div>
      <span class="eyebrow">Business Strategy & Execution</span>
      <h1>ASIS Business Ecigroup</h1>
      <p>
        Your Trusted Business Partner for Growth &amp; Excellence. We help ambitious companies
        clarify priorities, improve performance, and build resilient operations for the future.
      </p>
      <div class="hero-actions">
        <a class="button" href="/contact">Schedule a Consultation</a>
        <a class="button button--secondary" href="/services">Explore Services</a>
      </div>
      <ul class="pill-list">
        <li>Operational Excellence</li>
        <li>Advisory & Strategy</li>
        <li>Change Management</li>
      </ul>
    </div>

    <div class="hero-card card">
      <h2>Built for measurable outcomes</h2>
      <div class="grid stats-grid">
        <div>
          <strong>15+</strong>
          <p>Years guiding strategic business initiatives.</p>
        </div>
        <div>
          <strong>120+</strong>
          <p>Client engagements delivered across sectors.</p>
        </div>
        <div>
          <strong>92%</strong>
          <p>Client retention driven by trust and impact.</p>
        </div>
        <div>
          <strong>Global</strong>
          <p>Support for organizations operating across markets.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="section">
  <div class="container">
    <div class="section-heading center">
      <span class="eyebrow">Why Clients Choose Us</span>
      <h2 class="section-title">A practical partner for confident business decisions</h2>
      <p class="section-subtitle">
        We combine strategic thinking with hands-on delivery, helping leaders move from ideas to
        execution without losing focus on quality, speed, or long-term value.
      </p>
    </div>

    <div class="grid feature-grid">
      <article class="card">
        <div class="badge-icon">◆</div>
        <h3>Professional Services</h3>
        <p>
          Tailored consulting, planning, and implementation support aligned to your business model
          and operating environment.
        </p>
      </article>
      <article class="card">
        <div class="badge-icon">◎</div>
        <h3>Expert Team</h3>
        <p>
          Experienced advisors and project leaders with deep expertise in operations, growth, and
          business transformation.
        </p>
      </article>
      <article class="card">
        <div class="badge-icon">▲</div>
        <h3>Proven Results</h3>
        <p>
          We focus on performance metrics, execution milestones, and practical outcomes that create
          lasting business value.
        </p>
      </article>
      <article class="card">
        <div class="badge-icon">◌</div>
        <h3>Global Reach</h3>
        <p>
          Support for growing organizations navigating international markets, distributed teams,
          and cross-border operations.
        </p>
      </article>
    </div>
  </div>
</section>

<section class="section section--tight home-services">
  <div class="container">
    <div class="section-heading split-heading">
      <div>
        <span class="eyebrow">Core Capabilities</span>
        <h2 class="section-title">Services designed to unlock momentum</h2>
      </div>
      <a class="button button--secondary-dark" href="/services">View All Services</a>
    </div>

    <div class="grid service-grid">
      <article class="card">
        <div class="badge-icon">↗</div>
        <h3>Growth Strategy</h3>
        <p>
          Market expansion planning, revenue optimization, and growth roadmaps for business leaders
          preparing for the next stage.
        </p>
      </article>
      <article class="card">
        <div class="badge-icon">⚙</div>
        <h3>Operations Advisory</h3>
        <p>
          Process improvement, workflow design, and performance systems that increase efficiency
          across core business functions.
        </p>
      </article>
      <article class="card">
        <div class="badge-icon">☉</div>
        <h3>Transformation Delivery</h3>
        <p>
          Structured change programs that align teams, reduce risk, and accelerate adoption of new
          operating models.
        </p>
      </article>
    </div>
  </div>
</section>

<section class="section cta-band">
  <div class="container cta-card">
    <div>
      <span class="eyebrow">Ready to Move Forward</span>
      <h2>Build a stronger, more scalable business with the right partner.</h2>
      <p>
        From planning to execution, ASIS Business Ecigroup helps leadership teams navigate growth,
        refine operations, and create durable competitive advantage.
      </p>
    </div>
    <a class="button" href="/contact">Talk to Our Team</a>
  </div>
</section>

<section class="section newsletter-section">
  <div class="container newsletter-card card">
    <div>
      <span class="eyebrow">Insights & Updates</span>
      <h2 class="section-title">Stay informed with practical business insight</h2>
      <p>
        Join our newsletter for concise perspectives on strategy, operational improvement, and
        sustainable business growth.
      </p>
    </div>

    <form class="newsletter-form" on:submit|preventDefault={handleNewsletterSubmit}>
      <div class="form-group">
        <label for="newsletter-email">Business email</label>
        <input
          id="newsletter-email"
          type="email"
          bind:value={email}
          placeholder="name@company.com"
          aria-describedby="newsletter-feedback"
        />
      </div>
      <button class="button" type="submit">Subscribe</button>
    </form>

    {#if newsletterError}
      <p id="newsletter-feedback" class="error-text">{newsletterError}</p>
    {:else if newsletterMessage}
      <p id="newsletter-feedback" class="success-box">{newsletterMessage}</p>
    {/if}
  </div>
</section>

<style>
  .hero-grid,
  .cta-card,
  .newsletter-card {
    display: grid;
    gap: 2rem;
  }

  .hero-actions {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
    margin-top: 2rem;
  }

  .hero-card {
    background: rgba(255, 255, 255, 0.1);
    color: white;
    backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.15);
  }

  .hero-card h2,
  .cta-card h2 {
    margin-top: 0;
  }

  .hero-card strong {
    display: block;
    font-size: 1.6rem;
    color: var(--color-accent);
    margin-bottom: 0.35rem;
  }

  .center {
    text-align: center;
  }

  .split-heading {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 2rem;
  }

  .home-services {
    background: white;
  }

  .cta-band {
    background: linear-gradient(180deg, rgba(45, 106, 159, 0.08), rgba(30, 58, 95, 0.02));
  }

  .cta-card {
    align-items: center;
    padding: 2rem;
    border-radius: 1.4rem;
    background: var(--color-primary);
    color: white;
    box-shadow: var(--shadow-soft);
  }

  .cta-card p {
    color: rgba(255, 255, 255, 0.88);
  }

  .newsletter-section {
    padding-top: 0;
  }

  .newsletter-form {
    display: grid;
    gap: 1rem;
  }

  @media (min-width: 768px) {
    .hero-grid,
    .newsletter-card,
    .cta-card {
      grid-template-columns: repeat(2, minmax(0, 1fr));
      align-items: center;
    }

    .hero-actions,
    .split-heading {
      flex-direction: row;
      align-items: center;
      justify-content: space-between;
    }

    .newsletter-form {
      grid-template-columns: 1fr auto;
      align-items: end;
    }
  }
</style>
