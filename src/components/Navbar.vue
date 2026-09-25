<script setup>
import { ref } from 'vue'

const links = ['Product', 'Pricing', 'Docs', 'Changelog']
const open = ref(false)
</script>

<template>
  <header class="navbar">
    <div class="navbar-inner">
      <a class="brand" href="#">
        <span class="brand-mark">S</span>
        StoreHUBX
      </a>

      <nav class="links" :class="{ open }">
        <a v-for="link in links" :key="link" href="#">{{ link }}</a>
        <a class="cta" href="#">Sign in</a>
      </nav>

      <button
        class="toggle"
        type="button"
        :aria-expanded="open"
        aria-label="Toggle navigation"
        @click="open = !open"
      >
        <span />
        <span />
        <span />
      </button>
    </div>
  </header>
</template>

<style scoped>
.navbar {
  background: #12141c;
  border-bottom: 1px solid #262a38;
}

.navbar-inner {
  max-width: 960px;
  margin: 0 auto;
  padding: 0.9rem 1.25rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
}

.brand {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #f3f4f6;
  font-weight: 700;
  text-decoration: none;
  font-size: 1.05rem;
}

.brand-mark {
  width: 28px;
  height: 28px;
  border-radius: 8px;
  background: linear-gradient(135deg, #6366f1, #a855f7);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.9rem;
}

.links {
  display: flex;
  align-items: center;
  gap: 1.75rem;
}

.links a {
  color: #9ca3af;
  text-decoration: none;
  font-size: 0.9rem;
}

.links a:hover {
  color: #e5e7eb;
}

.links .cta {
  padding: 0.4rem 0.9rem;
  border-radius: 8px;
  background: #6366f1;
  color: #fff;
  font-weight: 600;
}

.links .cta:hover {
  background: #4f46e5;
  color: #fff;
}

.toggle {
  display: none;
  flex-direction: column;
  gap: 4px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.4rem;
}

.toggle span {
  width: 20px;
  height: 2px;
  background: #e5e7eb;
  border-radius: 1px;
}

@media (max-width: 640px) {
  .toggle {
    display: flex;
  }

  .links {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.25rem;
    background: #12141c;
    border-bottom: 1px solid #262a38;
    padding: 0.75rem 1.25rem 1rem;
    display: none;
  }

  .links.open {
    display: flex;
  }

  .links a {
    width: 100%;
    padding: 0.5rem 0;
  }

  .links .cta {
    width: 100%;
    text-align: center;
    margin-top: 0.4rem;
  }
}
</style>
