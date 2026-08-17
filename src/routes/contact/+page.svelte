<script lang="ts">
  type FormState = {
    name: string;
    email: string;
    subject: string;
    message: string;
  };

  let form: FormState = {
    name: '',
    email: '',
    subject: '',
    message: ''
  };

  let errors: Partial<FormState> = {};
  let successMessage = '';

  const validate = () => {
    const nextErrors: Partial<FormState> = {};

    if (!form.name.trim()) {
      nextErrors.name = 'Please enter your full name.';
    }

    if (!form.email.trim()) {
      nextErrors.email = 'Please enter your email address.';
    } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(form.email)) {
      nextErrors.email = 'Please provide a valid email address.';
    }

    if (!form.subject.trim()) {
      nextErrors.subject = 'Please add a subject for your enquiry.';
    }

    if (!form.message.trim()) {
      nextErrors.message = 'Please tell us a bit more about your needs.';
    } else if (form.message.trim().length < 20) {
      nextErrors.message = 'Please provide at least 20 characters so we can respond thoughtfully.';
    }

    errors = nextErrors;
    return Object.keys(nextErrors).length === 0;
  };

  const handleSubmit = () => {
    successMessage = '';

    if (!validate()) {
      return;
    }

    successMessage = `Thank you, ${form.name}. Your message has been prepared for our team. We will follow up shortly at ${form.email}.`;
    form = {
      name: '',
      email: '',
      subject: '',
      message: ''
    };
    errors = {};
  };
</script>

<svelte:head>
  <title>Contact | ASIS Business Ecigroup</title>
  <meta
    name="description"
    content="Contact ASIS Business Ecigroup to discuss strategy, operations, growth planning, or a tailored advisory engagement for your organization."
  />
  <link rel="canonical" href="https://asisbusinessecigroup.com/contact" />
</svelte:head>

<section class="page-hero">
  <div class="container">
    <span class="eyebrow">Get In Touch</span>
    <h1>Let’s discuss what your business needs next.</h1>
    <p>
      Whether you are planning for growth, improving operations, or seeking a strategic partner,
      we are ready to help you move forward with confidence.
    </p>
  </div>
</section>

<section class="section">
  <div class="container grid contact-grid">
    <article class="card">
      <h2 class="section-title">Send us a message</h2>
      <p>
        Share a few details about your goals, timeline, or current challenge. We will respond with
        the right next step.
      </p>

      <form class="contact-form" on:submit|preventDefault={handleSubmit} novalidate>
        <div class="form-group">
          <label for="name">Name</label>
          <input id="name" type="text" bind:value={form.name} placeholder="Your full name" />
          {#if errors.name}<span class="error-text">{errors.name}</span>{/if}
        </div>

        <div class="form-group">
          <label for="email">Email</label>
          <input id="email" type="email" bind:value={form.email} placeholder="name@company.com" />
          {#if errors.email}<span class="error-text">{errors.email}</span>{/if}
        </div>

        <div class="form-group">
          <label for="subject">Subject</label>
          <input id="subject" type="text" bind:value={form.subject} placeholder="How can we help?" />
          {#if errors.subject}<span class="error-text">{errors.subject}</span>{/if}
        </div>

        <div class="form-group">
          <label for="message">Message</label>
          <textarea
            id="message"
            rows="6"
            bind:value={form.message}
            placeholder="Tell us about your business goals, project, or challenge."
          ></textarea>
          {#if errors.message}<span class="error-text">{errors.message}</span>{/if}
        </div>

        <button class="button" type="submit">Submit enquiry</button>
      </form>

      {#if successMessage}
        <p class="success-box">{successMessage}</p>
      {/if}
    </article>

    <aside class="card contact-sidebar">
      <h2>Contact information</h2>
      <div class="info-stack">
        <div class="info-box">
          <strong>Email</strong>
          <p><a href="mailto:hello@asisbusinessecigroup.com">hello@asisbusinessecigroup.com</a></p>
        </div>
        <div class="info-box">
          <strong>Phone</strong>
          <p><a href="tel:+12125550198">+1 (212) 555-0198</a></p>
        </div>
        <div class="info-box">
          <strong>Office</strong>
          <p>1450 Market Growth Avenue, Suite 400, New York, NY 10018</p>
        </div>
      </div>

      <div>
        <h3>Follow us</h3>
        <ul class="social-list">
          <li><a href="https://www.linkedin.com" target="_blank" rel="noreferrer">LinkedIn</a></li>
          <li><a href="https://x.com" target="_blank" rel="noreferrer">X / Twitter</a></li>
          <li><a href="https://www.facebook.com" target="_blank" rel="noreferrer">Facebook</a></li>
        </ul>
      </div>
    </aside>
  </div>
</section>

<style>
  .contact-form,
  .info-stack,
  .social-list {
    display: grid;
    gap: 1rem;
  }

  .contact-sidebar {
    align-content: start;
  }

  .social-list {
    list-style: none;
    padding: 0;
  }

  .social-list a {
    color: var(--color-secondary);
    font-weight: 700;
  }
</style>
