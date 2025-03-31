<template>
    <div class="container">
        <div class="header bg-title">
            <h3 class="mt-4 text-center text-dark">Horario De Clases de Sistemas</h3>
        </div>

        <table class="table table-bordered text-center">
            <thead class="table-light">
                <tr>
                    <th scope="col">Hora</th>
                    <th scope="col">Lunes</th>
                    <th scope="col">Martes</th>
                    <th scope="col">Miércoles</th>
                    <th scope="col">Jueves</th>
                    <th scope="col">Viernes</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="clase in horario" :key="clase.hora">
                    <td>{{ clase.hora }}</td>
                    <td :class="getColorClass(clase.lunes)">{{ clase.lunes }}</td>
                    <td :class="getColorClass(clase.martes)">{{ clase.martes }}</td>
                    <td :class="getColorClass(clase.miercoles)">{{ clase.miercoles }}</td>
                    <td :class="getColorClass(clase.jueves)">{{ clase.jueves }}</td>
                    <td :class="getColorClass(clase.viernes)">{{ clase.viernes }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    setup() {
        const horario = ref([
            { hora: '7:00 - 9:00', lunes: 'Programación Lógica Funcional', martes: 'Inteligencia Artificial', miercoles: 'Desarrollo Ágil', jueves: 'Programación Lógica Funcional', viernes: '' },
            { hora: '9:00 - 11:00', lunes: 'Desarrollo Ágil', martes: 'Administración de Redes', miercoles: '', jueves: 'Administración de Redes', viernes: '' },
            { hora: '10:00 - 11:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Desarrollo Ágil' },
            { hora: '11:00 - 12:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Desarrollo en la Nube' },
            { hora: '11:00 - 13:00', lunes: '', martes: 'Desarrollo en la Nube', miercoles: 'Desarrollo en la Nube', jueves: 'Inteligencia Artificial', viernes: '' },
            { hora: '13:00 - 14:00', lunes: '', martes: '', miercoles: '', jueves: 'Desarrollo con Realidad Aumentada', viernes: '' },
            { hora: '13:00 - 15:00', lunes: '', martes: '', miercoles: 'Desarrollo con Realidad Aumentada', jueves: '', viernes: '' },
            { hora: '14:00 - 16:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Taller de Investigación' },
            { hora: '15:00 - 17:00', lunes: '', martes: 'Desarrollo con Realidad Aumentada', miercoles: 'Taller de Investigación', jueves: '', viernes: '' }
        ]);

        const getColorClass = (materia) => {
            const colores = {
                'Programación Lógica Funcional': 'bg-primary',
                'Inteligencia Artificial': 'bg-success',
                'Desarrollo Ágil': 'bg-info',
                'Administración de Redes': 'bg-warning',
                'Desarrollo en la Nube': 'bg-danger',
                'Desarrollo con Realidad Aumentada': 'bg-secondary',
                'Taller de Investigación': 'bg-light'
            };
            return colores[materia] || '';
        };

        return { horario, getColorClass };
    }
};
</script>

<style>
body {
    font-family: Arial, sans-serif;
    margin: 20px;
}
.bg-title {
    background-color: #a596da; /* Azul o el color que prefieras */
    padding: 15px;
    border-radius: 8px;
    text-align: center;
}
table {
    border-collapse: collapse;
    width: 100%;
    margin-top: 20px;
    font-style: normal;
    font-size: small;
}

th, td {
    border: 1px solid #007BFF;
    padding: 12px;
    text-align: center;
}

th {
    background-color: #030507;
    color: white;
}

tr:nth-child(even) {
    background-color: #f2f2f2;
}

tr:hover {
    background-color: #e2e2e2;
}

.bg-primary { background-color: #ac4f95; color: white; }
.bg-secondary { background-color: #6c757d; color: white; }
.bg-success { background-color: #28a745; color: white; }
.bg-info { background-color: #17a2b8; color: white; }
.bg-warning { background-color: #ffc107; color: black; }
.bg-danger { background-color: #dc3545; color: white; }
.bg-light { background-color: #f8f9fa; color: black; }
</style>