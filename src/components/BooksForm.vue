<template>
    <div class="form-group">
        <p>
            <label>Titulo:</label>
            <input v-model="titulo" type="text" placeholder="Insira o titulo" class="form-control">
        </p>
        <p>
            <label>ID:</label>
            <input v-model="id" type=number placeholder="Insira o ID" class="form-control">
        </p>
        <p>
            <label>Editora:</label>
            <input v-model="editora" type="text" placeholder="Insira a editora" class="form-control">
        </p>
        <div>
            <label>Numero de paginas:</label>
            <input v-model="numPaginas" type=number placeholder="Insira o numero de paginas" class="form-control">
        </div>
        <hr/>
        <button v-on:click="cadastrandoLivro" class="btn btn-primary">Cadastrar Livro</button>
    </div>
</template>

<script>
export default {
    name: "BooksForm",
    data(){
        return{
            titulo: '',
            id: null,
            editora: '',
            numPaginas: null,
        }
    },
    methods :{
        cadastrandoLivro(){
            if(this.titulo.trim() === '') {
                return;
            }
            else if(this.id.trim() === '') {
                return;
            }
            else if(this.editora.trim() === '') {
                return;
            }
            else if(this.numPaginas.trim() === '') {
                return;
            }
            this.$emit("emit-book", {titulo: this.titulo, id: this.id, editora: this.editora, numPaginas: this.numPaginas})
        }
    }
}
</script>