<script setup>
    const props = defineProps([
    'val1', 'val2', 'res'
    ]);
</script>

<template> 
    <form >
        <div class="row">
        <div class="col">
            <input @input="props.val1" type="number" placeholder="Digite o Primeiro valor" class="form-control">
        </div>
        </div>
        <div class="row">
        <div class="col mt-3 mb-3" >
            <input @input="props.val2" type="number" placeholder="Digite o Segundo valor" class="form-control">
        </div>
        </div>
        <div  class="col">
        <select @input="props.res" class="form-control">
            <option value="" disabled selected>Selecine uma expressão</option>
            <option value="+">Adição +</option>
            <option value="-">Subtração -</option>
            <option value="*">Multiplicação *</option>
            <option value="/">Divisão /</option>
            <option value="%">Resto da divisão %</option>
        </select>
        </div>
    </form>
</template>

<style>
form{
    text-align:center
}
</style>