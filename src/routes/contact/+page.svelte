<script lang="ts">
    const contactInfo = [
      {
        label: 'Phone',
        value: '8142546693',
        icon: '📞'
      },
      {
        label: 'Email',
        value: 'hello@santy.in',
        icon: '✉️'
      },
      {
        label: 'Location',
        value: 'Hyderabad, India',
        icon: '📍'
      }
    ];
  </script>
  
  <h2 class="section-title">Get in Touch</h2>
  
  <div class="contact-grid">
    {#each contactInfo as item}
      <div class="contact-card">
        <div class="icon">{item.icon}</div>
        <h3>{item.label}</h3>
        <p>{item.value}</p>
      </div>
    {/each}
  </div>
  
  <style>
    .section-title {
      text-align: center;
      margin: 2rem 0 1.5rem;
      font-size: 2rem;
    }
  
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 6rem;
      max-width: 960px;
      margin: 0 auto;
      padding: 1rem;
      justify-items: center;
    }
  
    .contact-card {
      background: #ffffff;
      border: 1px solid #ddd;
      border-radius: 12px;
      padding: 2rem;
      text-align: center;
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
      transition: transform 0.3s;
      width: 100%;
      max-width: 300px;
    }
  
    .contact-card:hover {
      transform: translateY(-5px);
    }
  
    .icon {
      font-size: 2rem;
      margin-bottom: 0.75rem;
    }
  
    h3 {
      margin: 0.25rem 0;
      font-size: 1.2rem;
      color: #007acc;
    }
  
    p {
      font-size: 1rem;
      color: #333;
      word-break: break-word;
    }
  
    @media (max-width: 768px) {
      .contact-grid {
        grid-template-columns: repeat(1, 1fr);
        gap: 1rem;
      }
    }
  
    @media (min-width: 769px) and (max-width: 1024px) {
      .contact-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }
  </style>
  