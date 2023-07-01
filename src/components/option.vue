<template>
    <div>
        <div>
            <input v-model="name"/>
            <button @click="addName">Adicionar Nome</button>
            <h1>{{formatedFone}}</h1>
        </div>

        <div>
            <ul>
                <li>{{name}}</li>
                <li>{{age}}</li>
            </ul>
        </div>
    
        <div>
            <ul>
                <li v-for="nome in Nomes">{{nome}}</li>
            </ul>
        </div>
    </div>
</template>

<script lang="ts">

export default {
    name: 'option',
    props: [
        'age'
    ],
    data(){
        return {
            name: 'Option Name',
            names: [
                'Daniel',
                'Nell'
            ],
            formatedFone: ''
        }
    },
    methods:{
        addName(){
            this.names.push(this.name)
        }
    },
    computed: {
       Nomes() {
            return this.names;
       }
    },
    watch: {
        name(newName: string){
            var Regex = /(\d{2})(\d)/;
            this.formatedFone = newName.replace(Regex,"($1) $2")
        }
    }
}
</script>