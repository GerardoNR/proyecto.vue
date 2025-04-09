<script>
export default {
    data() {
        return {
            alumnos: [
                { id: 12345, nombre: 'Gerardo', carrera: 'ISC', gusto: 'Básquet' },
                { id: 12346, nombre: 'Noe', carrera: 'Civil', gusto: 'Juegos' },
                { id: 12347, nombre: 'Jose', carrera: 'Industrial', gusto: 'Música' },
                { id: 12348, nombre: 'Aricel', carrera: 'Mecánica', gusto: 'Cine' },
                { id: 12349, nombre: 'Maria', carrera: 'ISC', gusto: 'Baile' },
                { id: 12350, nombre: 'Luis', carrera: 'IM', gusto: 'Lectura' },
                { id: 12351, nombre: 'Fernanda', carrera: 'Mecánica', gusto: 'Fotografía' },
                { id: 12352, nombre: 'Miguel', carrera: 'ISC', gusto: 'Cocina' },
                { id: 12353, nombre: 'Elena', carrera: 'Mecánica', gusto: 'Teatro' },
                { id: 12354, nombre: 'Roberto', carrera: 'Industrial', gusto: 'Natación' },
                { id: 12355, nombre: 'Gabriela', carrera: 'Civil', gusto: 'Pintura' },
                { id: 12356, nombre: 'Daniel', carrera: 'ISC', gusto: 'Ajedrez' },
                { id: 12357, nombre: 'Sofía', carrera: 'Civil', gusto: 'Senderismo' }
            ],
            horario: [
                { hora: '11:00-13:00', dias: ['Redes de Computadoras', 'LIBRE', 'Redes de Computadoras', 'Lenguajes y Autómatas I', 'Lenguajes y Autómatas I'] },
                { hora: '12:00-14:00', dias: ['LIBRE', 'Lenguajes y Autómatas I', 'LIBRE', 'LIBRE', 'LIBRE'] },
                { hora: '13:00-15:00', dias: ['Ingeniería de Software', 'LIBRE', 'LIBRE', 'Administración de Bases de Datos', 'Redes de Computadoras'] },
                { hora: '14:00-15:00', dias: ['LIBRE', 'LIBRE', 'LIBRE', 'LIBRE', 'Ingeniería de Software'] },
                { hora: '15:00-17:00', dias: ['Programación Web', 'Taller de Sistemas Operativos', 'Ingeniería de Software', 'Taller de Sistemas Operativos', 'Programación Web'] },
                { hora: '16:00-17:00', dias: ['Redes de Computadoras', 'LIBRE', 'LIBRE', 'LIBRE', 'LIBRE'] },
                { hora: '17:00-19:00', dias: ['Administración de Bases de Datos', 'Lenguajes de Interfaz', 'LIBRE', 'Lenguajes de Interfaz', 'Administración de Bases de Datos'] }
            ]
        };
    }
};
</script>

<template>
    <div class="container mt-4">
        <!-- LISTA DE ALUMNOS (PRIMERA SECCIÓN) -->
        <div class="card">
            <div class="card-header bg-primary text-white text-center">
                <h3>Lista de Alumnos</h3>
            </div>
            <div class="card-body">
                <div class="table-responsive">
                    <table class="table table-bordered table-striped">
                        <thead class="thead-dark">
                            <tr>
                                <th>No. Control</th>
                                <th>Nombre</th>
                                <th>Carrera</th>
                                <th>Gusto</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="alumno in alumnos" :key="alumno.id">
                                <td>{{ alumno.id }}</td>
                                <td>{{ alumno.nombre }}</td>
                                <td>{{ alumno.carrera }}</td>
                                <td>{{ alumno.gusto }}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <!-- HORARIO (SEGUNDA SECCIÓN) -->
        <div class="card mt-4">
            <div class="card-header bg-warning text-center">
                <h2>Horario</h2>
            </div>
            <div class="card-body">
              
                <div class="table-responsive">
                    <table class="table table-bordered text-center">
                        <thead>
                            <tr class="table-warning">
                                <th>Hora</th>
                                <th>Lunes</th>
                                <th>Martes</th>
                                <th>Miércoles</th>
                                <th>Jueves</th>
                                <th>Viernes</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(fila, index) in horario" :key="index">
                                <td class="fw-bold">{{ fila.hora }}</td>
                                <td v-for="(dia, i) in fila.dias" :key="i" :class="{ 'table-info': dia !== '' }">
                                    {{ dia || '-' }}
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* Estilos generales */
h3 {
    color: rgb(255, 255, 255);
}
/* Estilo para la tabla */
.table th {
    background-color: #0edde4;
    color: rgb(8, 8, 8);
}
/* Estilos para celdas alternas */
tr:nth-child(even) {
    background-color: #f2f2f2;
}
tr:nth-child(odd) {
    background-color: #ffffff;
}
/* Mejorando los botones */
button {
    font-size: 16px;
    padding: 10px 20px;
}
/* Estilos de tarjetas */
.card {
    border-radius: 10px;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
}
.card-header {
    font-weight: bold;
}
</style>