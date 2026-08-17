<svelte:head>
  <title>About | ASIS Business Ecigroup</title>
  <meta
    name="description"
    content="Learn about ASIS Business Ecigroup, our mission, values, leadership team, and commitment to helping businesses grow with confidence."
  />
  <link rel="canonical" href="https://asisbusinessecigroup.com/about" />
</svelte:head>

<script lang="ts">
  const team = [
    {
      name: 'Amara Johnson',
      role: 'Managing Director',
      bio: 'Amara leads strategic engagements and helps executive teams align growth ambitions with operational reality.'
    },
    {
      name: 'David Chen',
      role: 'Head of Operations Advisory',
      bio: 'David specializes in process optimization, performance systems, and building resilient operating models.'
    },
    {
      name: 'Sofia Mensah',
      role: 'Client Success Lead',
      bio: 'Sofia ensures every engagement is collaborative, well-governed, and focused on measurable client outcomes.'
    }
  ];

  const values = [
    'Integrity in every recommendation and decision',
    'Clarity that turns complexity into action',
    'Partnership rooted in trust and accountability',
    'Continuous improvement for long-term value',
    'Practical innovation that supports real execution',
    'Global perspective with local market awareness'
  ];

  const reasons = [
    'Senior-led delivery from discovery through implementation.',
    'Actionable frameworks instead of generic recommendations.',
    'Strong communication and governance throughout the engagement.',
    'A focus on measurable outcomes that matter to leadership teams.'
  ];
</script>

<section class="page-hero">
  <div class="container">
    <span class="eyebrow">About Our Firm</span>
    <h1>Helping organizations grow with clarity, discipline, and confidence.</h1>
    <p>
      ASIS Business Ecigroup was built to support leaders navigating change, growth, and the daily
      demands of running a high-performing organization.
    </p>
  </div>
</section>

<section class="section">
  <div class="container story-grid">
    <div>
      <span class="eyebrow">Our Story</span>
      <h2 class="section-title">A trusted advisory partner for modern business challenges</h2>
      <p>
        We founded ASIS Business Ecigroup to bridge the gap between strategic ambition and practical
        execution. Too often, organizations receive high-level advice without the systems, support,
        or implementation discipline required to make progress stick.
      </p>
      <p>
        Our team works alongside decision-makers to improve operations, sharpen strategy, and create
        sustainable momentum. We value thoughtful planning, honest dialogue, and results that stand
        up under real business pressure.
      </p>
    </div>

    <div class="card mission-card">
      <h3>Mission</h3>
      <p>
        To empower businesses with expert guidance, dependable execution support, and practical
        solutions that strengthen performance and long-term resilience.
      </p>
      <h3>Vision</h3>
      <p>
        To be the partner organizations trust when they need clarity, capability, and confidence to
        grow in a changing world.
      </p>
    </div>
  </div>
</section>

<section class="section section--tight team-section">
  <div class="container">
    <div class="section-heading center">
      <h2 class="section-title">Leadership team</h2>
      <p class="section-subtitle">
        Our leadership combines strategic expertise, operational experience, and a strong commitment
        to client success.
      </p>
    </div>

    <div class="grid team-grid">
      {#each team as member}
        <article class="card team-card">
          <div class="avatar">{member.name.split(' ').map((part) => part[0]).join('')}</div>
          <h3>{member.name}</h3>
          <p class="team-role">{member.role}</p>
          <p>{member.bio}</p>
        </article>
      {/each}
    </div>
  </div>
</section>

<section class="section values-section">
  <div class="container">
    <div class="section-heading center">
      <h2 class="section-title">Values that shape our work</h2>
      <p class="section-subtitle">
        These principles guide how we engage with clients, support teams, and build solutions that
        last.
      </p>
    </div>

    <div class="grid values-grid">
      {#each values as value}
        <article class="card">
          <div class="badge-icon">★</div>
          <p>{value}</p>
        </article>
      {/each}
    </div>
  </div>
</section>

<section class="section section--tight">
  <div class="container">
    <div class="section-heading center">
      <h2 class="section-title">Why choose us</h2>
    </div>

    <div class="grid why-grid">
      {#each reasons as reason}
        <article class="card why-card">
          <div class="badge-icon">✓</div>
          <p>{reason}</p>
        </article>
      {/each}
    </div>
  </div>
</section>

<style>
  .center {
    text-align: center;
  }

  .story-grid {
    display: grid;
    gap: 2rem;
    align-items: start;
  }

  .mission-card {
    background: linear-gradient(180deg, rgba(45, 106, 159, 0.08), rgba(30, 58, 95, 0.03));
  }

  .avatar {
    width: 4rem;
    height: 4rem;
    border-radius: 50%;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1rem;
    background: var(--color-primary);
    color: white;
    font-weight: 800;
  }

  .team-role {
    color: var(--color-secondary);
    font-weight: 700;
    margin-top: -0.35rem;
  }

  .team-section,
  .values-section {
    background: white;
  }

  @media (min-width: 768px) {
    .story-grid {
      grid-template-columns: 1.1fr 0.9fr;
    }
  }
</style>
