<template>
  <div id="cart">
    <nav-bar class="cart-nav">
      <div slot="center">
        购物车({{length}})
      </div>
    </nav-bar>
    <scroll class="content">
      <cart-list></cart-list>
    </scroll>
    <cart-bottom-bar></cart-bottom-bar>
  </div>
</template>

<script>
  import NavBar from 'components/common/navbar/NavBar'
  import Scroll from 'components/common/scroll/Scroll'

  import CartList from './childComps/CartList'
  import CartBottomBar from './childComps/CartBottomBar'

  import {mapGetters} from 'vuex'

  export default {
    name: "Cart",
    components: {
      NavBar,
      Scroll,
      CartList,
      CartBottomBar
    },
    computed: {
      ...mapGetters({
        length: 'cartLength',
        // cartList: 'cartList'
      })
    }
  }
</script>

<style scoped>
  #cart {
    height: 100vh;
    position: relative;
  }

  #cart .cart-nav {
    background-color: var(--color-tint);
    color: #fff;
  }

  #cart .content {
    position: absolute;
    top: 44px;
    bottom: 89px;
    left: 0;
    right: 0;
    overflow: hidden;
  }
</style>
