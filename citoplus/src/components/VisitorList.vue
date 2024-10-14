<template>
  <div>
    <h1>Lista de Visitantes</h1>
    
    <!-- Campo de búsqueda -->
    <input 
      type="text" 
      v-model="searchQuery" 
      placeholder="Buscar por nombre" 
    />

    <!-- Lista de visitantes filtrada -->
    <ul>
      <li v-for="(visitor, index) in filteredVisitors" :key="index">
        <strong>Nombre:</strong> {{ visitor.name }} <br />
        <strong>Fecha:</strong> {{ visitor.date }} <br />
        <strong>Identificación:</strong> {{ visitor.id }} <br />
        <hr />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // Texto ingresado en el campo de búsqueda
      searchQuery: "",
      
      // Lista de visitantes
      visitors: [
        { name: 'Juan Pérez', date: '2024-09-28', id: '123456789' },
        { name: 'Ana Gómez', date: '2024-09-27', id: '987654321' },
        { name: 'Carlos Rodríguez', date: '2024-09-26', id: '654123987' },
        { name: 'María Sánchez', date: '2024-09-25', id: '321789654' },
        { name: 'Luis Torres', date: '2024-09-24', id: '789456123' },
        { name: 'Claudia Ramírez', date: '2024-09-23', id: '159357246' },
        { name: 'Sergio Castro', date: '2024-09-22', id: '951753852' },
        { name: 'Gabriela Mendoza', date: '2024-09-21', id: '357951456' },
        { name: 'Ricardo López', date: '2024-09-20', id: '753159852' },
        { name: 'Natalia Duarte', date: '2024-09-19', id: '258456159' }
      ]
    };
  },
  
  computed: {
    // Filtra la lista de visitantes según el texto de búsqueda
    filteredVisitors() {
      return this.visitors.filter(visitor => 
        visitor.name.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
    }
  }
};
</script>

<style scoped>
h1 {
  font-family: Arial, sans-serif;
  color: #2c3e50;
}

input {
  margin-bottom: 20px;
  padding: 10px;
  width: 300px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin: 10px 0;
  font-family: Arial, sans-serif;
}

hr {
  border: 1px solid #ccc;
}
</style>
