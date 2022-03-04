<template>
  <q-list padding>
    <q-item exact clickable v-ripple to="/" exact-active-class="active">
      <q-item-section avatar>
        <q-icon name="fas fa-home" />
      </q-item-section>
      <q-item-section>
        Home
      </q-item-section>
    </q-item>

    <q-item exakt clickable v-ripple to="/ausbildung/nachweise" exact-active-class="active">
      <q-item-section avatar>
        <q-icon name="fas fa-book" />
      </q-item-section>
      <q-item-section>
        Ausbildungsnachweise
      </q-item-section>
    </q-item>
  </q-list>
</template>

<style scoped>
.active {
  color: lightgrey;
  font-weight: bold;
}
</style>
