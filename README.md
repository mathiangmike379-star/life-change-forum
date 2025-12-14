<!doctype html>
<html lang="en" class="h-full">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Life Change Forum</title>
  <meta name="description" content="Join Life Change Forum to transform your life through faith, spiritual growth, and meaningful connections.">
  <link rel="icon" href="/favicon.ico">

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- AOS Animations CSS -->
  <link href="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.css" rel="stylesheet">

  <!-- Custom styles -->
  <style>
    body { box-sizing: border-box; margin: 0; padding: 0; }
    .gradient-text {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .section-card { transition: transform 0.3s ease, box-shadow 0.3s ease; }
    .section-card:hover { transform: translateY(-4px); box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15); }
    .cta-button { transition: all 0.3s ease; }
    .cta-button:hover { transform: scale(1.05); box-shadow: 0 8px 16px rgba(102, 126, 234, 0.3); }
    html { scroll-behavior: smooth; }
  </style>

  <!-- Structured Data -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Organization",
    "name": "Life Change Forum",
    "url": "https://yourwebsite.com",
    "sameAs": ["https://facebook.com/yourpage","https://twitter.com/yourhandle"]
  }
  </script>
</head>
<body class="h-full">

<div id="root" class="h-full w-full overflow-auto"></div>

<!-- Floating chat button -->
<div id="floating-chat" class="fixed bottom-6 right-6 z-50">
  <button id="chat-btn" aria-label="Join the Life Change Forum community" class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-5 rounded-full shadow-lg transition-transform transform">
    💬 Join the Chat
  </button>
</div>

<!-- Chat modal -->
<div id="chat-modal" class="hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
  <div class="bg-white rounded-xl p-8 max-w-md w-full shadow-lg relative">
    <button id="close-modal" class="absolute top-3 right-3 text-gray-500 hover:text-gray-700 font-bold text-lg">&times;</button>
    <h2 class="text-2xl font-bold mb-4" style="color: #1e40af;">Join Our Community</h2>
    <p class="mb-6" style="color: #1e293b;">Enter your email to get updates or start chatting with members of the forum.</p>
    <input type="email" placeholder="Your email" class="w-full p-3 mb-4 border border-gray-300 rounded-lg" />
    <button class="w-full bg-blue-600 hover:bg-blue-700 text-white py-3 rounded-lg font-semibold">Subscribe / Join</button>
  </div>
</div>

<!-- Scripts -->
<script src="https://cdn.jsdelivr.net/npm/aos@2.3.4/dist/aos.js"></script>
<script>
  AOS.init({ duration: 1000, once: true, easing: 'ease-out-cubic' });

  const chatBtn = document.getElementById('chat-btn');
  const chatModal = document.getElementById('chat-modal');
  const closeModal = document.getElementById('close-modal');
  setInterval(() => { chatBtn.classList.toggle('scale-105'); }, 2000);

  chatBtn.addEventListener('click', () => chatModal.classList.remove('hidden'));
  closeModal.addEventListener('click', () => chatModal.classList.add('hidden'));
  chatModal.addEventListener('click', (e) => { if (e.target === chatModal) chatModal.classList.add('hidden'); });

  const defaultConfig = {
    background_color: "#ffffff",
    card_color: "#f8fafc",
    text_color: "#1e293b",
    primary_action_color: "#2563eb",
    secondary_action_color: "#1e40af",
    font_family: "Inter",
    font_size: 16,
    main_title: "Life Change Forum",
    subtitle: "Transform Your Life Through Faith and Community",
    hero_message: "Join a professional community dedicated to spiritual growth, meaningful connections, and lasting transformation through faith-based principles.",
    about_title: "About Our Forum",
    about_text: "Life Change Forum provides a structured platform for individuals seeking spiritual development and personal transformation. We facilitate meaningful discussions, provide resources, and foster connections that lead to lasting positive change.",
    cta_button: "Join the Community",
    footer_text: "Transforming Lives Together"
  };

  async function onConfigChange(config) {
    const root = document.getElementById('root');
    const backgroundColor = config.background_color || defaultConfig.background_color;
    const cardColor = config.card_color || defaultConfig.card_color;
    const textColor = config.text_color || defaultConfig.text_color;
    const primaryColor = config.primary_action_color || defaultConfig.primary_action_color;
    const secondaryColor = config.secondary_action_color || defaultConfig.secondary_action_color;
    const fontFamily = config.font_family || defaultConfig.font_family;
    const baseSize = config.font_size || defaultConfig.font_size;

    const mainTitle = config.main_title || defaultConfig.main_title;
    const subtitle = config.subtitle || defaultConfig.subtitle;
    const heroMessage = config.hero_message || defaultConfig.hero_message;
    const aboutTitle = config.about_title || defaultConfig.about_title;
    const aboutText = config.about_text || defaultConfig.about_text;
    const ctaButton = config.cta_button || defaultConfig.cta_button;
    const footerText = config.footer_text || defaultConfig.footer_text;

    root.style.backgroundColor = backgroundColor;
    root.style.color = textColor;
    root.style.fontFamily = `${fontFamily}, Georgia, serif`;

    root.innerHTML = `
      <div class="w-full">
        <!-- Hero Section -->
        <header class="flex flex-col md:flex-row items-center py-16 px-6 md:px-12" style="background: linear-gradient(135deg, ${primaryColor} 0%, ${secondaryColor} 100%);">
          <div class="md:w-1/2 text-center md:text-left" data-aos="fade-right">
            <div class="mb-4 text-white font-semibold tracking-widest uppercase" style="font-size: ${baseSize * 0.9}px;" data-aos="fade-down">${subtitle}</div>
            <h1 class="gradient-text text-4xl md:text-6xl font-bold mb-6" data-aos="fade-up">${mainTitle}</h1>
            <p class="text-white mb-8" style="font-size: ${baseSize * 1.1}px;" data-aos="fade-up" data-aos-delay="200">${heroMessage}</p>
            <button class="cta-button px-6 py-3 rounded-lg text-white font-semibold" style="background-color: ${primaryColor};" data-aos="zoom-in" data-aos-delay="400">${ctaButton}</button>
          </div>
          <div class="md:w-1/2 mt-8 md:mt-0 flex justify-center" data-aos="fade-left">
            <img src="https://via.placeholder.com/400x300" alt="People engaging in a faith-based community" loading="lazy" class="rounded-xl shadow-lg" />
          </div>
        </header>

        <!-- Features Section -->
        <section class="py-16 px-6 max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="section-card bg-white rounded-xl p-6 shadow-md text-center" data-aos="fade-up">
            <h3 class="text-xl font-bold mb-2" style="color: ${secondaryColor};">Spiritual Growth</h3>
            <p style="color: ${textColor}; font-size: ${baseSize}px;">Access resources, discussions, and guides to deepen your faith and personal growth.</p>
          </div>
          <div class="section-card bg-white rounded-xl p-6 shadow-md text-center" data-aos="fade-up" data-aos-delay="100">
            <h3 class="text-xl font-bold mb-2" style="color: ${secondaryColor};">Meaningful Connections</h3>
            <p style="color: ${textColor}; font-size: ${baseSize}px;">Engage with a supportive community of like-minded individuals.</p>
          </div>
          <div class="section-card bg-white rounded-xl p-6 shadow-md text-center" data-aos="fade-up" data-aos-delay="200">
            <h3 class="text-xl font-bold mb-2" style="color: ${secondaryColor};">Lasting Transformation</h3>
            <p style="color: ${textColor}; font-size: ${baseSize}px;">Participate in challenges and programs designed to bring real-life positive change.</p>
          </div>
        </section>

        <!-- About Section -->
        <section class="py-16 px-6 max-w-4xl mx-auto">
          <div class="section-card bg-white rounded-xl p-8 shadow-md" data-aos="fade-up">
            <h2 class="text-2xl font-bold mb-4" style="color: ${secondaryColor};">${aboutTitle}</h2>
            <p style="font-size: ${baseSize}px; color: ${textColor};">${aboutText}</p>
          </div>
        </section>

        <!-- Testimonials Section -->
        <section class="py-16 px-6 max-w-6xl mx-auto">
          <h2 class="text-3xl font-bold text-center mb-12" style="color: ${secondaryColor};" data-aos="fade-up">What Our Members Say</h2>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div class="section-card bg-white rounded-xl p-6 shadow-md" data-aos="fade-up">
              <p class="italic mb-4" style="color: ${textColor};">"Life Change Forum has completely transformed my perspective and daily habits. I feel more connected spiritually."</p>
              <h4 class="font-bold" style="color: ${secondaryColor};">– Alice W.</h4>
            </div>
            <div class="section-card bg-white rounded-xl p-6 shadow-md" data-aos="fade-up" data-aos-delay="100">
              <p class="italic mb-4" style="color: ${textColor};">"The community here is amazing. I’ve built friendships and grown so much in faith."</p>
              <h4 class="font-bold" style="color: ${secondaryColor};">– John D.</h4>
            </div>
            <div class="section-card bg-white rounded-xl p-6 shadow-md" data-aos="fade-up" data-aos-delay="200">
              <p class="italic mb-4" style="color: ${textColor};">"I love the structured programs. They really help me put my faith into action daily."</p>
              <h4 class="font-bold" style="color: ${secondaryColor};">– Mary K.</h4>
            </div>
          </div>
        </section>

        <!-- Footer -->
        <footer class="text-center py-8" style="background-color: ${cardColor}; color: ${textColor}; font-size: ${baseSize}px;">
          ${footerText}
        </footer>
      </div>
    `;
  }

  onConfigChange(defaultConfig);
</script>
</body>
</html>