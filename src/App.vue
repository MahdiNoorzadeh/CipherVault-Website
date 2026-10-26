<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)

const links = {
  repo: 'https://github.com/MahdiNoorzadeh/CipherVault',
  releases: 'https://github.com/MahdiNoorzadeh/CipherVault/releases',
  setup: 'https://github.com/MahdiNoorzadeh/CipherVault/blob/main/SETUPGUIDE.md',
  readme: 'https://github.com/MahdiNoorzadeh/CipherVault#readme',
}

const features = [
  { icon: '◈', title: 'Encrypted by design', text: 'Token values are encrypted with AES-256-GCM before they are stored locally.' },
  { icon: '⌘', title: 'Keys stay in your keyring', text: 'The master encryption key is managed through your operating system keyring.' },
  { icon: '▦', title: 'Projects, not piles', text: 'Keep credentials grouped by project, service, and the environment they belong to.' },
  { icon: '⇄', title: 'Production ≠ Development', text: 'Separate environments so the right credential is easier to find at the right time.' },
  { icon: '◉', title: 'Reveal only when needed', text: 'Show or hide token values, and copy credentials when you need them.' },
  { icon: '☼', title: 'A workspace that fits', text: 'Choose a dark or light interface to suit your working environment.' },
]
</script>

<template>
  <main>
    <section class="hero-shell" id="top">
      <nav class="nav container" aria-label="Main navigation">
        <a class="brand" href="#top" aria-label="CipherVault home">
          <span class="brand-mark"><img src="/ciphervault-icon.png" alt="" /></span>
          <span>Cipher<span>Vault</span></span>
        </a>
        <button class="menu-toggle" type="button" :aria-expanded="menuOpen" aria-label="Toggle navigation" @click="menuOpen = !menuOpen">☰</button>
        <div class="nav-links" :class="{ 'nav-links-open': menuOpen }">
          <a href="#features" @click="menuOpen = false">Features</a>
          <a href="#how-it-works" @click="menuOpen = false">How it works</a>
          <a :href="links.readme" target="_blank" rel="noreferrer">Documentation ↗</a>
          <a class="nav-cta" :href="links.releases" target="_blank" rel="noreferrer">Get CipherVault <span>↗</span></a>
        </div>
      </nav>

      <div class="hero container">
        <div class="hero-copy">
          <div class="eyebrow"><span class="status-dot"></span> THE QUIETER WAY TO HANDLE SECRETS</div>
          <h1>Your API keys.<br /><span>In order.</span></h1>
          <p class="hero-lede">A focused desktop workspace for the API tokens behind your projects—organized by project and environment, with encrypted local storage.</p>
          <div class="hero-actions">
            <a class="button button-primary" :href="links.releases" target="_blank" rel="noreferrer">Explore downloads <span>↗</span></a>
            <a class="button button-ghost" :href="links.repo" target="_blank" rel="noreferrer"><span class="github-mark">⌘</span> View source</a>
          </div>
          <div class="hero-meta"><span><i class="mini-check">✓</i> Desktop-first</span><span><i class="mini-check">✓</i> Open source</span><span><i class="mini-check">✓</i> MIT license</span></div>
        </div>

        <div class="hero-visual" aria-label="CipherVault application icon and security highlights">
          <div class="visual-orbit orbit-one"></div>
          <div class="visual-orbit orbit-two"></div>
          <div class="visual-glow"></div>
          <div class="hero-icon-frame">
            <img class="hero-app-icon" src="/ciphervault-icon.png" alt="CipherVault shield and lock application icon" />
          </div>
          <div class="visual-chip chip-encryption"><span class="chip-symbol">⌁</span><span><b>AES-256-GCM</b><small>Token encryption</small></span></div>
          <div class="visual-chip chip-keyring"><span class="chip-symbol">▣</span><span><b>OS keyring</b><small>Key management</small></span></div>
          <div class="visual-caption"><span class="caption-dot"></span> DESKTOP-FIRST · LOCAL WORKSPACE</div>
        </div>
      </div>
      <div class="hero-bottom container"><span>BUILT FOR DEVELOPERS WHO SHIP</span><div class="hero-tech"><span>Electron</span><i></i><span>Vue 3</span><i></i><span>AES-256-GCM</span><i></i><span>Realm</span></div></div>
    </section>

    <section class="intro-section section-pad">
      <div class="container intro-grid"><div><div class="section-kicker">LESS HUNTING. MORE BUILDING.</div><h2>Stop losing time<br />to <span>secret sprawl.</span></h2></div><div class="intro-copy"><p>Development moves fast. Credentials end up scattered across notes, terminals, and project folders. CipherVault gives your API tokens a dedicated home—with a clear structure for the work you do every day.</p><a class="text-link" href="#features">Meet your new workflow <span>→</span></a></div></div>
    </section>

    <section class="features-section section-pad" id="features">
      <div class="container"><div class="section-heading"><div><div class="section-kicker">MADE FOR THE DAILY LOOP</div><h2>Small details.<br /><span>Better workflow.</span></h2></div><p>Useful controls, thoughtful organization, and security features that work quietly in the background.</p></div>
        <div class="feature-grid"><article v-for="feature in features" :key="feature.title" class="feature-card"><div class="feature-icon">{{ feature.icon }}</div><h3>{{ feature.title }}</h3><p>{{ feature.text }}</p><span class="card-corner">↗</span></article></div>
      </div>
    </section>

    <section class="security-section section-pad" id="how-it-works"><div class="container security-grid"><div class="security-copy"><div class="section-kicker light-kicker">SECURITY THAT STAYS OUT OF YOUR WAY</div><h2>Your secrets<br />aren't <span>the product.</span></h2><p>CipherVault is designed as a local desktop tool. Token values are encrypted before storage, and the master key is managed through your operating system's keyring.</p><a class="button button-outline" :href="links.readme" target="_blank" rel="noreferrer">Read the security overview <span>↗</span></a></div><div class="security-steps"><article><div class="step-number">01</div><div><h3>Organize</h3><p>Create projects and separate credentials by environment.</p></div><span class="step-symbol">▦</span></article><article><div class="step-number">02</div><div><h3>Protect</h3><p>Token values are encrypted with AES-256-GCM for local storage.</p></div><span class="step-symbol">◇</span></article><article><div class="step-number">03</div><div><h3>Use when needed</h3><p>Reveal or copy the credential from your desktop workspace.</p></div><span class="step-symbol">↗</span></article><div class="security-note"><span>ⓘ</span> Security depends on your device, operating system, and how you manage access to them.</div></div></div></section>

    <section class="docs-section section-pad"><div class="container"><div class="section-heading docs-heading"><div><div class="section-kicker">GOOD TO KNOW</div><h2>Everything you need<br />to <span>get started.</span></h2></div><p>Explore the code, learn the setup process, or find the latest available release.</p></div><div class="resource-grid"><a class="resource-card" :href="links.releases" target="_blank" rel="noreferrer"><div class="resource-icon">↓</div><div><span class="resource-label">DOWNLOADS</span><h3>Get the desktop app</h3><p>Browse the official releases and available installers.</p></div><span class="resource-arrow">↗</span></a><a class="resource-card" :href="links.setup" target="_blank" rel="noreferrer"><div class="resource-icon">⌘</div><div><span class="resource-label">DOCUMENTATION</span><h3>Installation & setup</h3><p>Follow the setup guide and troubleshooting notes.</p></div><span class="resource-arrow">↗</span></a><a class="resource-card" :href="links.repo" target="_blank" rel="noreferrer"><div class="resource-icon">⌁</div><div><span class="resource-label">OPEN SOURCE</span><h3>Explore the repository</h3><p>Review the code and contribute on GitHub.</p></div><span class="resource-arrow">↗</span></a></div></div></section>

    <section class="final-cta"><div class="container final-cta-inner"><div class="cta-mark"><img src="/ciphervault-icon.png" alt="" /></div><div><div class="section-kicker light-kicker">YOUR WORKSPACE, A LITTLE MORE ORDERED</div><h2>Keep your keys close.<br /><span>Keep your focus closer.</span></h2><p>Make your API credentials easier to manage, one project at a time.</p></div><a class="button button-primary" :href="links.releases" target="_blank" rel="noreferrer">Explore releases <span>↗</span></a></div></section>

    <footer class="footer"><div class="container footer-main"><a class="brand footer-brand" href="#top"><span class="brand-mark"><img src="/ciphervault-icon.png" alt="" /></span><span>Cipher<span>Vault</span></span></a><p>A dedicated home for your API tokens.</p><div class="footer-links"><a :href="links.repo" target="_blank" rel="noreferrer">GitHub</a><a :href="links.releases" target="_blank" rel="noreferrer">Releases</a><a :href="links.readme" target="_blank" rel="noreferrer">README</a></div></div><div class="container footer-bottom"><span>© {{ new Date().getFullYear() }} CipherVault</span><span>Open source · MIT License</span><a href="#top">Back to top ↑</a></div></footer>
  </main>
</template>
