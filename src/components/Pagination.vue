<template>
    <div class="button-container">
      <button @click="changePage(currentPage - 1)" :disabled="currentPage === 1"><</button>
      <button v-for="page in totalPages" :key="page" @click="changePage(page)" :disabled="currentPage === page">{{ page }}</button>
      <button @click="changePage(currentPage + 1)" :disabled="currentPage === totalPages">></button>
    </div>
  </template>
  
  <script>
  
  export default {
    props: {
      totalPages: {
        type: Number,
        required: true
      },
      currentPage: {
        type: Number,
        required: true
      }
    },
    setup(props, { emit }) {
      const changePage = (pageNumber) => {
        if (pageNumber >= 1 && pageNumber <= props.totalPages) {
          emit('pageChanged', pageNumber);
        }
      };
  
      return {
        changePage
      };
    }
  };
  </script>

<style>
    .button-container{
        display: flex;
        justify-content: center;
        gap: 10px;
    }

    .button-container button{ 
        background-color: transparent;
        width: 64px;
        height: 64px;
        border: 1px solid #999999; 
        border-radius: 5px; 
        color: #999999; 
        padding: 20px;
        cursor: pointer;
        transition: background-color 0.3s ease; 
    }

    .button-container button:hover  {
    background-color: #007bff;
    color: #ffffff;
    }
</style>
    