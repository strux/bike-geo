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
                        <v-switch :color="bike.color" v-model="bike.enabled"></v-switch>
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
                    enabled: true,
                    color: 'red',
                    make: 'Evil',
                    model: 'The Following',
                    wheelSize: 622,
                    wheelBase: 1139,
                    stack: 608,
                    reach: 435,
                    chainStay: 430,
                    bbHeight: 338,
                },
                {
                    enabled: true,
                    color: 'blue',
                    make: 'Evil',
                    model: 'The Calling',
                    wheelSize: 584,
                    wheelBase: 1170,
                    stack: 601,
                    reach: 440,
                    chainStay: 430,
                    bbHeight: 338,
                },
            ]
        }
    }
}
</script>
