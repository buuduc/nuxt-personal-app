<template>
    <v-app-bar scroll-behavior="hide" scroll-threshold="10">
        <template v-slot:image>
            <v-img gradient="to top right, rgba(19,84,122,.8), rgba(128,208,199,.8)"></v-img>
        </template>
        <NuxtLink to="/">
            <v-app-bar-nav-icon icon="mdi-home"></v-app-bar-nav-icon>
        </NuxtLink>

        <!-- <template v-slot:prepend>
                </template> -->

        <v-app-bar-title>My Personal Site</v-app-bar-title>

        <v-spacer></v-spacer>
        <nuxt-link  to="/animations"> animations </nuxt-link >
        <nuxt-link  to="/happy-new-year-2024"> Happy new year </nuxt-link >

        <v-btn icon>
            <v-icon>mdi-magnify</v-icon>
        </v-btn>



        <v-btn icon>
            <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
    </v-app-bar>

    <v-main>
        <slot />
    </v-main>
</template>
