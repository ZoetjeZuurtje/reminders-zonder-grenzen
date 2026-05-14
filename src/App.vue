<script setup lang="ts">
import Header from './components/Header.vue'
import Countdown from './components/Countdown.vue'

// const targetDate = new Date('2026-05-13T18:00:00Z')
const year = new Date().getFullYear()
</script>

<template>
    <Header />
    <main id="center">
      <section class="mission">
        <h2>Duo hasn't forgotten.</h2>
        <p class="lead">It will never</p><br>
          <Countdown />
        
      </section>

      <section class="stats">
        <div class="card">
          <div class="num">12k+</div>
          <div class="label">Reminders</div>
        </div>
        <div class="card">
          <div class="num">0</div>
          <div class="label">Places to hide</div>
        </div>
        <div class="card">
          <div class="num">3.9/5</div>
          <div class="label">User satisfaction</div>
        </div>
      </section>

      <section class="cta">
        <div class="cta-left">
          <h3>Support our mission</h3>
          <p>Even a small contribution can help us reach more people, more often than they'd want.</p>
          <a class="donate" href="https://steun.artsenzondergrenzen.nl/doe-een-gift" target="_blank" rel="noopener noreferrer">Donate</a>
        </div>
        <div class="cta-right">
          <blockquote>
          "This initiative reminded me to disable notifications, unsubscribe from mailing lists, and power off my phone for a bit."
        </blockquote>
        <p>—Anonymous, ungrateful customer</p>
        </div>
      </section>

    </main>

    <footer>
      <div id="spacer"></div>
      <div class="footer-inner" style="padding:20px; text-align:center; color:var(--text);">
  <div>© {{ year }} Reminders zonder Grenzen</div>
        <div style="margin-top:6px;">Made with ❤️ and careful intentions</div>
        <div style="margin-top:8px;"><a href="https://github.com/ZoetjeZuurtje" target="_blank" rel="noopener noreferrer">GitHub /ZoetjeZuurtje</a></div>
      </div>
    </footer>
</template>
