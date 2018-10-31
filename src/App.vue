<template>
    <v-app dark>
        <v-navigation-drawer
            v-model="drawer"
            fixed
            right
            permanent
            app
            >
            <v-list>
                <v-list-tile
                    v-for="bike in bikes"
                    :key="bike.model"
                    >
                    <v-list-tile-content>
                        <v-list-tile-title><span style="caption">{{bike.make}}</span> {{bike.model}}</v-list-tile-title>
                    </v-list-tile-content>
                    <v-list-tile-action>
                        <v-switch color="red" v-model="bike.enabled"></v-switch>
                    </v-list-tile-action>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
        <v-content>
            <geo-vizualizer v-bind:bikes="bikes"></geo-vizualizer>
        </v-content>
    </v-app>
</template>

<script>
import GeoVizualizer from './components/GeoVizualizer'

export default {
    name: 'App',
    components: {
        GeoVizualizer,
    },
    data () {
        return {
            bikes: [
                {
                    color: 'red',
                    make: 'Evil',
                    model: 'The Following',
                    enabled: true,
                    wheelSize: 622,
                },
                {
                    color: 'blue',
                    make: 'Evil',
                    model: 'The Calling',
                    enabled: true,
                    wheelSize: 584,
                },
            ]
        }
    }
}
</script>
