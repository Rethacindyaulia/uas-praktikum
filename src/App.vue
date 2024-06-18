<template>
  <div class="q-pa-md">
    <q-btn-dropdown color="purple" label="Dropdown Button" dropdown-icon="^">
      <q-list class="nav-list">
        <q-item clickable v-close-popup>
          <router-link to="/">
            <q-item-section>
              <q-item-label>Weather</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas1">
            <q-item-section>
              <q-item-label>Tugas 1</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas2">
            <q-item-section>
              <q-item-label>Tugas 2</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas3">
            <q-item-section>
              <q-item-label>Tugas 3</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas4">
            <q-item-section>
              <q-item-label>Tugas 4</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas5">
            <q-item-section>
              <q-item-label>Tugas 5</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas6">
            <q-item-section>
              <q-item-label>Tugas 6</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>

        <q-item clickable v-close-popup>
          <router-link to="/tugas7">
            <q-item-section>
              <q-item-label>Tugas 7</q-item-label>
            </q-item-section>
          </router-link>
        </q-item>
      </q-list>
    </q-btn-dropdown>

    <router-view></router-view>
  </div>
</template>

<script>
export default {
  setup() {

  }
};
</script>