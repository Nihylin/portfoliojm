<template>
  <section class="contact">
    <h2>Contact</h2>
    <p>Vers : JeanMichelDeLaMuerte@gmail.fr</p>
    <form @submit.prevent="handleSubmit()">
        <label for="raison">Motif : </label>
        <select name="raisons" id="raison" v-model="raisons" @input="raisons_dirty = true">
            <option value="">-- C'est pour quoi? :> --</option>
            <option value="work">Job? Job??? Un job??!</option>
            <option value="blabla">Papoter</option>
            <option value="cpf">Arnaque au CPF</option>
            <option value="conj">Bannir le résultat d'une conjuration ratée</option>
        </select>
        <small v-show="raisonsError" class="error">Veuillez choisir un motif</small>
        <label for="content">Contenu du message</label>
        <textarea name="text" id="content" cols="30" rows="10" v-model.trim="content" @input="content_dirty = true"></textarea>
        <small v-show="contentError" class="error">'faut remplir le champ de texte, monsieur/dame</small>
        <button :disabled="formError">Envoyer</button>
    </form>
  </section>
</template>

<script>
    export default {
        name:'ContactComponent',
        data: function(){
            return{
                raisons:undefined,
                content:undefined,
                raisons_dirty:false,
                content_dirty:false
            }
        },
        methods:{
            handleSubmit:function(){
                console.log("Message envoyé !");
            }
        },
        computed:{
            raisonsError:function(){
                return !this.raisons && this.raisons_dirty;
            },
            contentError:function(){
                return !this.content && this.content_dirty;
            },
            formError:function(){
                return !this.content_dirty || !this.raisons_dirty || this.raisonsError || this.contentError
            }
        }
    }
</script>

<style scoped>

</style>
