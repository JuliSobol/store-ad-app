<template>
    <v-container>
        <v-layout row>
            <v-flex xs12 sm6 offset-sm3>
                <h1 class="text--secondary md-3">My Ads</h1>

                <v-card 
                    v-for="ad in ads"
                    :key="ad.id"
                    class="elevation-10 mb-3">
                    <v-layout row>

                        <v-flex xs4>
                            <v-img
                                :src="ad.imageSrc"
                                height="160px"
                            ></v-img>
                        </v-flex>

                        <v-flex xs8>
                            <v-card-text>
                                <h2 class="text--primary">{{ad.title}}</h2>
                                <p>{{ad.description}}</p>
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer></v-spacer>
                                <v-btn 
                                    :to="/ad/ + ad.id"
                                    class="info">Open</v-btn>
                            </v-card-actions>                            
                        </v-flex>

                    </v-layout>
                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data () {
        return {
             ads: [
                {
                    title: 'First ad',
                    description: 'Hello i am description',
                    promo: false,
                    imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
                    id: '1'
                },
                {
                    title: 'Second ad',
                    description: 'Hello i am description',
                    promo: true,
                    imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
                    id: '2'
                },
                {
                    title: 'Third ad',
                    description: 'Hello i am description',
                    promo: true,
                    imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
                    id: '3'
                }
            ]
        }
    }
}
</script>