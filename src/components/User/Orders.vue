<template>
    <v-container>
        <v-layout>
            <v-flex xs12 sm6 offset-sm3>

                <h1 class="text--secondary mb-3">Orders</h1>
                <v-list subheader two-line>

                    <v-list-tile
                        avatar
                        v-for="order in orders"
                        :key="order.id"
                    >
                        <v-list-tile-action>
                            <v-checkbox
                                color="primary"
                                :input-value="order.done"
                                @change="markDone(order)"
                            ></v-checkbox>
                        </v-list-tile-action>

                        <v-list-tile-content>
                            <v-list-tile-title>{{ order.name }}</v-list-tile-title>
                            <v-list-tile-sub-title>{{ order.phone }}</v-list-tile-sub-title>
                        </v-list-tile-content>

                        <v-list-tile-action>
                            <v-btn
                                class="primary"
                                :to="'/ad/' + order.adId"
                            >Open</v-btn>
                        </v-list-tile-action>
                    </v-list-tile>

                </v-list>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
  data () {
    return {
      orders: [
        {
          id: 'fds',
          name: 'Komil',
          phone: '8-925-332-00-96',
          adId: '123',
          done: false
        }
      ]
    }
  },
  methods: {
    markDone (order) {
      order.done = true
    }
  }
}
</script>
