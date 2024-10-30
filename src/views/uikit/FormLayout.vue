<script>
export default {
    data() {
        return {
            firstName: '',
            lastName: '',
            motherName: '',
            birthDate: '',
            rfc: ''
        };
    },
    methods: {
        generateRFC() {
            // Aquí puedes agregar la lógica para generar el RFC
            this.rfc = `${this.lastName.slice(0, 2).toUpperCase()}${this.motherName.slice(0, 1).toUpperCase()}${this.firstName.slice(0, 1).toUpperCase()}${this.birthDate.replace(/-/g, '').slice(2, 8)}`;
        }
    }
};
</script>

<template>
    <div class="container mx-auto max-w-md p-6 bg-white shadow-md rounded-md">
        <h2 class="text-xl font-bold mb-6">GENERAR EL RFC DE UNA PERSONA</h2>
        <form @submit.prevent="generateRFC">
            <div class="mb-4">
                <label for="firstName" class="block text-gray-700">Nombre(s):</label>
                <input v-model="firstName" id="firstName" type="text" class="input-field" required />
            </div>
            <div class="mb-4">
                <label for="lastName" class="block text-gray-700">Apellido Paterno:</label>
                <input v-model="lastName" id="lastName" type="text" class="input-field" required />
            </div>
            <div class="mb-4">
                <label for="motherName" class="block text-gray-700">Apellido Materno:</label>
                <input v-model="motherName" id="motherName" type="text" class="input-field" />
            </div>
            <div class="mb-4">
                <label for="birthDate" class="block text-gray-700">Fecha Nacimiento:</label>
                <input v-model="birthDate" id="birthDate" type="date" class="input-field" required />
            </div>
            <div class="mb-4">
                <label for="rfc" class="block text-gray-700">RFC</label>
                <input v-model="rfc" id="rfc" type="text" class="input-field" readonly />
            </div>
            <button type="submit" class="bg-green-500 text-white w-full py-2 rounded-md">GENERAR</button>
        </form>
    </div>
</template>

<style scoped>
.container {
    background-color: #f9fafb;
}
.input-field {
    width: 100%;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
}
</style>
