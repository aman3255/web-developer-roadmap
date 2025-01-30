# 🛍️ E-commerce Frontend (2025 Edition)  
*Vue.js 3.4 + TypeScript + Pinia + Tailwind CSS*  

![Vue.js](https://img.shields.io/badge/Vue.js-3.4-brightgreen)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.0-06B6D4)
![Pinia](https://img.shields.io/badge/Pinia-2.1-orange)

A future-ready frontend for the E-commerce App featuring:  
- **Role-based UI** (Admin/User)  
- **AI-powered search** with vector embeddings  
- **Web3-ready authentication**  
- **Offline-first** favorites system  

---

## 🚀 Features  
**2025-Ready Frontend**  
- 🧑💻 Admin dashboard with real-time analytics  
- 🔍 Hybrid search (text + semantic similarity)  
- 📱 Responsive + Adaptive Design (Desktop/Tablet/VR)  
- 🛡️ JWT authentication with refresh token rotation  
- 📬 Contact form with AI-assisted issue categorization  

**Core Functionality**  
- Role-based access control (RBAC)  
- Product CRUD operations (Admin)  
- Favorites system with localForage persistence  
- Dynamic filtering & sorting  
- Dark/light mode toggle  

---

## 🧰 Tech Stack  

| Category          | Tools                                                                 |  
|-------------------|-----------------------------------------------------------------------|  
| **Framework**     | Vue.js 3.4 (Composition API + `<script setup>`)                       |  
| **State**         | Pinia 2.1 + Pinia-ORM (TypeScript-first)                              |  
| **Styling**       | Tailwind CSS 4.0 + DaisyUI (Component library)                        |  
| **Auth**          | VueUse + Web3Modal (WalletConnect/Magic.link)                         |  
| **Search**        | Meilisearch + OpenAI embeddings                                       |  
| **Testing**       | Vitest + Testing Library + Cypress 12                                 |  

---

## 🎨 UI/UX Highlights  

### 1. **AI-Powered Product Search**  
```vue
<!-- components/SearchBar.vue -->
<script setup lang="ts">
const search = useSearchStore();

// Hybrid search: text + vector similarity
await search.findProducts({
  query: "gaming laptop",
  maxPrice: 2000,
  similarityThreshold: 0.85
});
</script>
