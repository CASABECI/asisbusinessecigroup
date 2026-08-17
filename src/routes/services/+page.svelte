<svelte:head>
  <title>Services | ASIS Business Ecigroup</title>
  <meta
    name="description"
    content="Explore ASIS Business Ecigroup services including strategy, operations, transformation, market expansion, governance, and performance advisory."
  />
  <link rel="canonical" href="https://asisbusinessecigroup.com/services" />
</svelte:head>

<script lang="ts">
  const services = [
    {
      icon: '↗',
      title: 'Business Growth Strategy',
      description:
        'Growth plans grounded in market insight, commercial priorities, and realistic execution steps.'
    },
    {
      icon: '⚙',
      title: 'Operational Improvement',
      description:
        'Process redesign, workflow optimization, and capability building to improve efficiency and control.'
    },
    {
      icon: '☉',
      title: 'Transformation Programs',
      description:
        'End-to-end change delivery that helps organizations modernize systems, structures, and ways of working.'
    },
    {
      icon: '▣',
      title: 'Corporate Governance Support',
      description:
        'Decision frameworks, reporting structures, and oversight practices that support resilient leadership.'
    },
    {
      icon: '◈',
      title: 'Market Expansion Advisory',
      description:
        'Guidance for entering new regions, evaluating partnerships, and positioning your business for scale.'
    },
    {
      icon: '✓',
      title: 'Performance Management',
      description:
        'KPIs, dashboards, and accountability systems to keep strategy connected to measurable outcomes.'
    }
  ];
</script>

<section class="page-hero">
  <div class="container">
    <span class="eyebrow">Professional Services</span>
    <h1>Solutions built around performance, resilience, and growth.</h1>
    <p>
      We help businesses solve practical challenges, scale thoughtfully, and strengthen the systems
      that support sustainable success.
    </p>
  </div>
</section>

<section class="section">
  <div class="container">
    <div class="section-heading center">
      <h2 class="section-title">What we deliver</h2>
      <p class="section-subtitle">
        Every engagement is tailored to your operating context, goals, and growth stage. Our work
        combines strategic clarity with implementation discipline.
      </p>
    </div>

    <div class="grid service-grid">
      {#each services as service}
        <article class="card service-card">
          <div class="badge-icon">{service.icon}</div>
          <h3>{service.title}</h3>
          <p>{service.description}</p>
          <a href="/contact">Discuss this service →</a>
        </article>
      {/each}
    </div>
  </div>
</section>

<section class="section section--tight">
  <div class="container delivery-strip card">
    <div>
      <h2>Need a tailored engagement model?</h2>
      <p>
        We can support one-time advisory work, project-based delivery, leadership workshops, or
        longer-term strategic partnerships.
      </p>
    </div>
    <a class="button" href="/contact">Request a Proposal</a>
  </div>
</section>

<style>
  .center {
    text-align: center;
  }

  .service-card {
    position: relative;
    overflow: hidden;
  }

  .service-card::after {
    content: '';
    position: absolute;
    inset: auto 0 0;
    height: 4px;
    background: linear-gradient(90deg, var(--color-accent), var(--color-secondary));
    transform: scaleX(0);
    transform-origin: left;
    transition: var(--transition);
  }

  .service-card:hover::after {
    transform: scaleX(1);
  }

  .service-card a {
    display: inline-flex;
    margin-top: 1rem;
    color: var(--color-secondary);
    font-weight: 700;
  }

  .delivery-strip {
    display: grid;
    gap: 1.5rem;
    align-items: center;
    background: linear-gradient(135deg, rgba(45, 106, 159, 0.08), rgba(240, 165, 0, 0.12));
  }

  @media (min-width: 768px) {
    .delivery-strip {
      grid-template-columns: 1fr auto;
    }
  }
</style>
