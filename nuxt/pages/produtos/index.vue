<template>
    <div>
        <h1 class="text-lg font-bold">Produtos</h1>
        <p>jnsfvjnfvlçdsfvklçdfvjnlsdfvçklndfvsklnçdvfslnkç dsfçlvndfçlvknsdflçvn sdfçlvnsdçlfnvçlsdfn sdlfvnsdçlfnvlsdnvç sçdlnvsçldvnsdlçfnv slvnsdfl</p>                   
    

        <div v-for="product in products" :key="product.id" class="border-b border-gray-400 py-3">
            {{ products.title }}
        </div>
    </div>
</template>

<script>

export default {
    name: '', 

    data() {
        return {

        };
    },

    async asyncData({ $axios }) {
        
        const products = await $axios.$get('https://jsonplaceholder.typicode.com/posts')

        return {
            products,
        }
    },

    methods: {

    },
};
</script>
