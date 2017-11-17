<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <div>
          <ul>
              <Category name="Domestico" :todos="[todo[0], todo[3]]"/>
              <Category name="Laboral" :todos="[todo[1]]"/>
              <Category name="Social" :todos="[todo[2]]"/>

          </ul>
      </div>
  </div>
</template>

<script>
    import Category from "./Category";
    export default {
      name: 'HelloWorld',
      data () {
        return {
            msg: 'Lista TODOS',
            todo: ['Ir al mercadona', 'Preparar la clase', 'Felicitar a Luci', "Fregar"]
        }
      },
      components: {
        Category
      }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->


<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}

</style>

<!-- sass:
    $my-var: 5em;

    #main{
        width: $my-var;
        Ó...
        width: $my-var !default; Si ya existía my-var, se coge el valor que ya tenía.
    }

    @extends //no admite variables, se usa cuando se use en clases semánticamente iguales (para botones, por ejemplo).
             //Si los elementos están alejados mñas de 100 líneas, usar mixing.
        .button{
            color: azul;
        }

       .warning{

   @extends.button
        color: rojo;
   }

   @mixing(){
    ...
   }

    .mixing{
        @include button;
         ...
    }

    @extends y mixing para hacer overwrite cuando ocurre un warning;

    //OPERACIONES:
    font-weigth: $font-base + 2em;

    //FUNCIONES
    @import "./archivoAImportar"
    Se prioriza lo de más abajo.

    //MEDIA QUERY
    .a{
        define a en genérico
        @media nq{
            define a en media query
        }
    }

    //IF
    @mixing button ($border:false){ //con $border = true || $border = false después del : parámetro por defecto
        @ifborder {...}
    }


-->