<template>
  <header>
    <v-app-bar app flat class="transparent">
      <v-container class="d-flex align-center pa-0">
        <div id="brand" class="pa-2">
          <nuxt-link to="/">
            <v-img :src="brand"></v-img>
          </nuxt-link>
        </div>
        <v-spacer />
        <v-btn class="d-sm-none" icon @click.stop="rightDrawer = !rightDrawer">
          <v-icon>mdi-menu</v-icon>
        </v-btn>
        <v-list class="appNav d-none d-sm-flex transparent pa-0">
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            :to="item.to"
            class="py-1"
          >
            <v-list-item-content class="px-0">
              <v-list-item-title v-text="item.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <div class="px-3 d-none d-sm-flex align-center">
          <v-btn block depressed href="/" dark rounded color="secondary"
            >Logout</v-btn
          >
        </div>
      </v-container>
    </v-app-bar>
    <v-navigation-drawer v-model="rightDrawer" temporary fixed>
      <v-list class="drawer">
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to">
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </header>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'Laman Admin',
          to: '/',
        },
        {
          title: 'Beranda',
          to: '/inspire',
        },
      ],
      rightDrawer: false,
      brand: require('@/assets/images/topBrand.png'),
    }
  },
}
</script>

<style>
#brand {
  max-width: 150px;
}

.appNav .v-list-item--link:before {
  background-color: transparent;
}
.appNav .v-list-item--active {
  font-weight: bold;
  opacity: 1;
}
.appNav a {
  opacity: 0.7;
}
.appNav a:hover {
  opacity: 1;
}

.drawer .v-list-item--active {
  color: green;
  font-weight: bold;
}

.drawer a:hover {
  opacity: 0.9;
}
</style>
