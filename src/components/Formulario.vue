<template>
<div id="app">
    <div class="formulario">
    <form>
        <label for="titulo">Título: </label>
        <input type="text" v-model="titulo" />
        <br />
        <hr />
        <label for="emoji">Emoji: </label>
        <select v-model="emoji">
        <option value="💻">💻</option>
        <option value="👩‍💻">👩‍💻</option>
        <option value="👨‍💻">👨‍💻</option>
        </select>
        <br />
        <hr />
        <label for="apreciacion">Apreciación:</label>
        <input type="radio" v-model="apreciacion" value="Regular" />Regular
        <input type="radio" v-model="apreciacion" value="Bien" />Bien
        <input type="radio" v-model="apreciacion" value="muyBien" />Muy bien
        <input type="radio" v-model="apreciacion" value="Increible" />Increíble
        <br />
        <hr />
        <div class="container-checkbox">
        <label for="competencias">Competencias aprendidas:</label>
        <div class="checkbox-input">
            <input type="checkbox" v-model="competencias" value="Morfologia"/>Morfologia de un componente
            <input type="checkbox" v-model="competencias" value="OneWay"/>One-Way y Two-Way data binding
            <input type="checkbox" v-model="competencias" value="Patron" />El patrón de diseño MVVM
            <input type="checkbox" v-model="competencias" value="Directivas"/>EDirectivas
            <input type="checkbox" v-model="competencias" value="Estado" />Estado
        </div>
        </div>
        <br />
        <hr />
        <div class="form-group">
        <label for="opinion">Opinión: </label>
        <textarea v-model="opinion" id="opinion"></textarea>
        </div>
    </form>
    </div>

    <div class="resultados">
    <p>{{ emoji }}</p>
    <p><strong>{{ titulo }}</strong></p>
    <p><strong>Y me parece </strong>{{ apreciacion }}</p>
    <p><strong>He aprendido:</strong> 
    <span v-if="competencias.length">[{{ competencias.join(", ") }}]</span></p>
    <p><strong>Mi opinión hasta ahora del framework es: <br> </strong>{{ opinion }}</p>
    </div>
</div>
</template>

<script>
export default {
name: "Formulario",
data() {
    return {
    titulo: "",
    emoji: "",
    apreciacion: "",
    competencias: [],
    opinion: "",
    };
},
};
</script>

<style scoped>
#app {
display: flex;
width: 100%;
gap: 20px;
}

.resultados {
width: 50%;
display: flex;
flex-direction: column;
gap: 10px;
border: 1px solid #000;
border-radius: 10px;
padding: 10px;
text-align: center;
}

.formulario {
width: 50%;
background-color: #000;
color: #fff;
border-radius: 10px;
border: 1px solid #ccc;
padding: 20px;
}

#opinion {
width: 450px;
height: 50px;
margin-top: 20px;
}

.form-group {
display: flex;
align-items: center;
gap: 10px;
}

.container-checkbox {
display: flex;
}

.checkbox-input {
display: flex;
flex-wrap: wrap;
gap: 10px;
margin-left: 15px;
}
</style>
