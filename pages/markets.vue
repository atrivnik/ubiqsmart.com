<template>
  <b-row class="justify-content-md-center">
    <b-col md="12">
      <b-card class="card-main">
        <b-row no-gutters class="market-section">
          <b-col md="5">
            <div class="section-content">
              <h4>{{ $t("markets.title") }}</h4>
              <hr/>
              <p v-html="$t('markets.text1')"/>
              <p v-html="$t('markets.text2')"/>
            </div>
          </b-col>
          <b-col md="7" class="market-graphic">
            <img src="~/assets/monetary-policy.svg" width="80%">
          </b-col>
        </b-row>
      </b-card>
      <b-card class="card-market" v-for="(item, index) in markets" :key="index">
        <a :href="item.url" target="_blank">
          <b-row>
            <b-col md="3" class="img-market-col">
              <div class="flex-vh-center">
                <img :src="require('~/assets/markets/' + item.id + '.png')"/>
              </div>
            </b-col>
            <b-col md="9" class="text-market-col">
              <div class="section-content">
                <h4>{{ $t("markets." + item.id + ".title") }}</h4>
                <hr/>
                <p>{{ $t("markets." + item.id + ".text") }}</p>
              </div>
            </b-col>
          </b-row>
        </a>
      </b-card>
    </b-col>
  </b-row>
</template>

<script>
export default {
  name: 'Markets',
  data () {
    return {
      // id used to reference image and translation data.
      markets: [{
        id: 'bittrex',
        url: 'https://bittrex.com/'
      }, {
        id: 'changeangel',
        url: 'https://changeangel.io/'
      }, {
        id: 'litebit',
        url: 'https://www.litebit.eu/en'
      }, {
        id: 'catalx',
        url: 'https://catalx.io/'
      }, {
        id: 'xchange',
        url: 'https://xchange.me/'
      }, {
        id: 'simpleswap',
        url: 'https://simpleswap.io/'
      }, {
        id: 'stealthex',
        url: 'https://stealthex.io/'
      }, {
        id: 'swapspace',
        url: 'https://swapspace.co/'
      }]
    }
  }
}
</script>
