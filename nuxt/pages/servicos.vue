<template>
    <div>
        <h1 class="text-lg font-bold">Serviços</h1>

        <NuxtLink to="/servicos/desenvolvimento-de-sites">Desenvolvimento de sites</NuxtLink>
        <NuxtLink to="/servicos/marketing-digital">Marketing digital</NuxtLink>
        
        <br><br>

        <pre>
            {{ $fetchState }}
        </pre>

        <pre>
            {{ services }}
        </pre>

        <NuxtChild />      
    </div>
</template>

<script>

export default {
    name: '', 

    head() {
        return {
            title: this.title,
            meta: [
                { hid: 'description', name: 'description', content: 'Minha descrição dos serviços' }
            ],
            bodyAttrs: {
                class: 'bg-gray-400'
            }
        }
    },

    data() {
        return {
            title: '',
            services:[]
        };
    },

    async fetch() {
        this.services = await this.$axios.$get('https://jsonplaceholder.typicode.com/users')
    },

    created() {
        this.getTitle()
    },

    methods: {
        getTitle() {
            setTimeout(() => {
                this.title = 'Serviços'
            }, 3000)
        }
    },
};
</script>
