<template>
    <v-container class="pa-0 pb-5">
        <v-layout wrap align-center justify-center row fill-height>
            
            <v-flex xs12 md12 class="mt-2">
                <p class="google-font my-2" style="font-size:110%">Our Sponsors</p>
                <v-layout row wrap class="transparent">
                    <v-flex xs12 sm7 class="elevation-0 transparent">
                        <v-card class="elevation-0 pa-0 ma-0 transparent">
                            <v-container grid-list-sm fluid class="pa-0 ma-0">
                                <v-layout row wrap class="ma-0 pa-0">
                                    <v-flex
                                        v-for="(itemp,i) in partnerData" :key="i"
                                        xs6
                                        md3
                                        sm4
                                        d-flex
                                        class="pa-0 white elevation-0" 
                                    >
                                    <!-- style="border-radius:5px;border-color:#e0e0e0;border-width: 1px; border-style: solid;" -->
                                    <v-card flat tile class="d-flex pa-2 ma-1 elevation-1" style="border-radius:4px;border-width: 0px; border-style: solid;">
                                        
                                        <a v-bind:href="itemp.link" target="_blank" >
                                            <v-tooltip bottom>
                                            <template v-slot:activator="{ on }">
                                            <v-img
                                            :src="getImgUrl(itemp.img)"
                                            :lazy-src="getImgUrl(itemp.img)"
                                            aspect-ratio="3.0"
                                            class="white"
                                            v-on="on"
                                            >
                                                <v-layout
                                                    slot="placeholder"
                                                    fill-height
                                                    align-center
                                                    justify-center
                                                    ma-0
                                                >
                                                    <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                                                </v-layout>
                                            </v-img>
                                            </template>
                                            <span class="google-font">{{itemp.name}}</span>
                                            </v-tooltip>
                                        </a>
                                        
                                    </v-card>
                                    </v-flex>

                                </v-layout>
                            </v-container>
                        </v-card>
                    </v-flex>
                </v-layout>

            </v-flex>

        </v-layout>
    </v-container>
</template>

<script>
import datap from '@/assets/data/sponsors.json'
import chapterDetails from '@/assets/data/chapterDetails.json'
export default {
    data() {
        return {
            partnerData: datap,
            chapterDetails: chapterDetails
        }
    },
    methods:{
        getImgUrl(pic) {
            return require('@/assets/img/sponsors/'+pic)
        },
    }
}
</script>