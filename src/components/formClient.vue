<template>
    <form class="form" @submit="cadastroCliente" >
        <div class="input-container">
            <label for="name">Nome:</label>
            <input type="text" id="name" v-model="name" placeholder="Insira o nome" required>
        </div>
        <div class="input-container">
            <label for="doc">Documento:</label>
            <input type="text" id="doc" v-model="doc" placeholder="Insira número do documento" required>
        </div>
        <div class="input-container">
            <label for="phone">Telefone:</label>
            <input type="text" id="phone" v-model="phone" placeholder="Insira o telefone" required>
        </div>
        <div class="input-container">
            <label for="mail">E-mail:</label>
            <input type="email" id="mail" v-model="mail" placeholder="Insira o e-mail" required>
        </div>

        <div class="input-radio">
            <input type="checkbox" id="checkbox" v-model="checked">
            <label for="checkbox"> Ativo</label>
        </div> <br>

        <div class="input-container">
            <input type="submit" class="btn-success" value="Cadatrar">
        </div>

    </form>
</template>

<script>
    export default {
        name: 'formClient',
        data(){
            return{
                name: null,
                doc: null,
                phone: null,
                mail: null,
                checked: true,
                msg: null
            }
        },
        methods:{
            async cadastroCliente(e){
                e.preventDefault();

                const data = {
                    name: this.name,
                    doc: this.doc,
                    phone: this.phone,
                    mail: this.mail,
                    checked: this.checked,
                    status: "Solicitado"
                }

                const dataJson = JSON.stringify(data);

                const request = await fetch("http://localhost:3000/clients", {
                    method: "POST",
                    headers: {'Content-Type':'application/json'},
                    body: dataJson
                });

                const result = await request.json();
                this.name = "";
                this.doc = "";
                this.phone = "";
                this.mail = "";
                this.checked = false;
            }
        }
    }
</script>

<style scoped>
    .form{
        max-width: 40%;
        margin: 0 auto;
    }

    .input-container{
        display: flex;
        flex-direction: column;
    }

    .input-container input{
        min-width: 100%;
        padding: 1% 0;
        margin-bottom: 3%;
    }

    label{
        display: contents;
        font-size: 0.9em;
        font-weight: bold;
    }

    .btn-success{
        background-color: rgb(242, 129, 0);
        color: #fff; 
        min-width: 50% !important;
        padding: 2% 0 !important;
        font-weight: bold;
        cursor: pointer;
    }

    .btn-success:hover{
        transition: .5s;
        background-color: rgb(230, 167, 96);
        color: #fff; 
    }
</style>