<template>
  <div class="app-container">
    <aside class="sidebar">
      <h2>Chindy Aurella Taniya</h2>
      <ul>
        <li v-for="(item, index) in menu" :key="index" @click="current = item.component">
          {{ item.title }}
        </li>
      </ul>
    </aside>
    <main class="content-area">
      <component :is="current" />
    </main>
  </div>
</template>

<script>
import Declarative from './components/Declarative.vue'
import Attribute from './components/Attribute.vue'
import Form from './components/Form.vue'
import Conditional from './components/Conditional.vue'
import List from './components/List.vue'
import Computed from './components/Computed.vue'
import LifecycleRefs from './components/LifecycleRefs.vue'
import Watchers from './components/Watchers.vue'

export default {
  components: {
    Home,
    Declarative,
    Attribute,
    Form,
    Conditional,
    List,
    Computed,
    LifecycleRefs,
    Watchers
  },
  data() {
    return {
      menu: [
        { title: 'Declarative Rendering', component: 'Declarative' },
        { title: 'Attribute Bindings', component: 'Attribute' },
        { title: 'Form Bindings', component: 'Form' },
        { title: 'Conditional Rendering', component: 'Conditional' },
        { title: 'List Rendering', component: 'List' },
        { title: 'Computed Property', component: 'Computed' },
        { title: 'Lifecycle dan Template Refs', component: 'LifecycleRefs' },
        { title: 'Watchers', component: 'Watchers' },
      ],
      current: 'Computed' // untuk menampilkan Computed.vue saat pertama kali
    }
  }
}
</script>

<style scoped>
.app-container {
  display: flex;
  min-height: 100vh;
  font-family: 'Segoe UI', sans-serif;
}

.sidebar {
  width: 250px;
  background: linear-gradient(to bottom, #4f4f4f, #2f2f2f); /* Gradasi abu-abu */
  color: #f0f0f0;
  padding: 1.5rem;
  box-shadow: 4px 0 10px rgba(0, 0, 0, 0.2);
  border-right: 1px solid #5a5a5a;
}

.sidebar h2 {
  margin-bottom: 1.5rem;
  font-size: 1.6rem;
  text-align: center;
  font-weight: bold;
  color: #ffffff;
  border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  padding-bottom: 0.5rem;
}

.sidebar ul {
  list-style: none;
  padding: 0;
}

.sidebar li {
  cursor: pointer;
  padding: 12px;
  border-radius: 8px;
  margin-bottom: 10px;
  transition: background 0.3s, transform 0.2s;
  background-color: rgba(255, 255, 255, 0.05);
}

.sidebar li:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateX(5px);
}

.content-area {
  flex: 1;
  padding: 2rem;
  background: linear-gradient(to right, #e0e0e0, #f5f5f5); /* Gradasi abu-abu muda */
  color: #333;
  overflow-y: auto;
  border-left: 1px solid #d0d0d0;
}

</style>
