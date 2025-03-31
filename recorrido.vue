<script>  
export default {  
  data() {  
    return {  
     
      alumnos: [   
      { id: 1, nombreComplete: 'Jeronima Roque Cballero', carrera: 'ISC', email: 'jerocaballero@gmail.com' },
        { id: 2, nombreComplete: 'Margarita Roque Caballero', carrera: 'IT', email: 'magoroque12@gmail.com' },
        { id: 3, nombreComplete: 'Dayana Mendez Roque', carrera: 'ISC', email: 'dayana12@gmail.com' },
        { id: 4, nombreComplete: 'Gerardo Reyes Ortis', carrera: 'ISC', email: 'gerardo134@gmail.com' },
        { id: 5, nombreComplete: 'Gael Roque Hernandez', carrera: 'ITC', email: 'gaelRoque1@gmail.com' },
        { id: 6, nombreComplete: 'Osvaldo Roque Hernandez', carrera: 'IT', email: 'osvahrdz@gmail.com' },
        { id: 7, nombreComplete: 'Efrain Ramirez Perez', carrera: 'ITC', email: 'Efra123@gmail.com' } 
      ]  
    }  
  }  
}  
</script> 

<template>  
  <div class="container">  
    <h3 class="mt-4" >Lista de alumnos</h3>  
    <ul>  
      <li v-for="alumno in alumnos" :key="alumno.id"> 
        <strong>ID:</strong>{{ alumno.id }} 
        <strong>Nombre:</strong>{{ alumno.nombreCompleto }} 
        <strong>Carrera:</strong>{{ alumno.carrera }} 
        <strong>Email:</strong>{{ alumno.email }} 
      </li>  
    </ul>  
  </div>  
</template>   
<style>  
h3 {  
  color: rgb(19, 13, 13);  
  background-color: rgb(73, 34, 94);  
  border-radius: 15px;  
  padding: 10px;  
  text-align: center;
}  

ul {  
  list-style-type: none;  
  padding: 0%;  
}  

li {  
  color: white;  
  background-color: rgb(163, 60, 60);  
  border-radius: 15px;  
  padding: 10px;  
  margin: 10px;  
 text-align: center;
}  
</style>  