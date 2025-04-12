<template>
    <div class="welcome-container">
      <h3>Bienvenido a mi pagina</h3>
    </div>
  </template>
  
  <style scoped>
  
  .welcome-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #a6d1b5; 
    color: #333; 
    text-align: center;
    padding: 20px;
    border-radius: 8px; 
  }
  
  
  .welcome-container h3 {
    font-size: 1.8rem; 
    font-family: 'Arial', sans-serif;
    font-weight: 400; 
    color: #333; 
    margin: 0;
    padding: 10px 20px;
    background-color: #b88b8b; 
    border-radius: 8px; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
    transition: all 0.3s ease; 
  }
  
  
  .welcome-container h3:hover {
    background-color: #ff8c00; 
    color: white; 
    transform: scale(1.05); 
  }
  </style>
  