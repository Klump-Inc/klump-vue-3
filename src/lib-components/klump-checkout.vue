<script>
export default /*#__PURE__*/ {
    name: 'KlumpCheckout',
    props: {
        devMode:{
            type: Boolean,
            default: false
        }
    },
    methods:{
        payWithKlump() {
           this.$emit('on-click')
		},
    },
    mounted() {
        const klumpScript = document.createElement("script");
        klumpScript.src = this.devMode ? "https://staging-js.useklump.com/klump.js" : "https://js.useklump.com/klump.js";
        document.head.appendChild(klumpScript)
    }
}
</script>

<template>
   <div id="klump__checkout" @click="payWithKlump"/>
</template>

