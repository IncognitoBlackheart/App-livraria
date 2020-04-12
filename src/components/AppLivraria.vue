<template>
    <div class="container">
        <h1>Livros</h1>
        <hr/>

        <BooksForm v-on:emit-book="cadastrandoLivro" />

        <div v-for="(l, index) in books" :key="index">
            <span>Titulo: <strong>{{ l.titulo }}</strong></span>
            <div>ID: <strong>{{ l.id }}</strong></div>
            <div>Editora: <strong>{{ l.editora }}</strong></div>
            <div>Numero de paginas: <strong>{{ l.numPaginas }}</strong></div>
            <div>
                <a v-on:click.prevent="removendoLivro(index)" href="#">Remover</a>
            </div>
            <hr/>
        </div>
    </div>
</template>

<script>

import BooksForm from './BooksForm';

export default {
    name: "Books",
    components:{
        BooksForm
    },
    data(){
        return{
            books: []
        }
    },
    methods: {
        cadastrandoLivro(book){
            this.books.push(book);
        },
        removendoLivro(index){
            this.books.splice(index, 1);
        }
    }
}
</script>