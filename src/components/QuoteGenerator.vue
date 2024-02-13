<template>
    <div class="container">
      <h1>{{ quote }}</h1>
      <button @click="generateQuote">Get New Quote</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const quote = ref('');
  const color = ref('');
  
  const quotes = [
    "The giving of love is an education in itself.",
    "We are most alive when we are in love.",
    "Love does not dominate; it cultivates.",
    "Who being loved, is poor?",
    "If I know what love is, it is because of you.",
    "You are so beautiful it hurts.",
    "A true love story never ends."
  ];
  
  function generateQuote() {
    const randomQuoteIndex = Math.floor(Math.random() * quotes.length);
    quote.value = quotes[randomQuoteIndex];
  
    const hexChars = '0123456789ABCDEF';
    let randomColor = '#';
    for (let i = 0; i < 6; i++) {
      randomColor += hexChars[Math.floor(Math.random() * 16)];
    }
    color.value = randomColor;
    document.body.style.color = color.value; // Set body color using reactive ref
  }
  </script>
  
  <style scoped>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }
  
  h1 {
    font-size: 50px;
    font-family: serif;
    font-style: italic;
    margin-bottom: 30px;
  }
  
  button {
    border-radius: 30px;
    width: 100px;
    height: 30px;
    border: 5px solid red;
    font-size: 10px;
    background-color: transparent;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
  }
  
  button:hover {
    border-color: black;
  }
  </style>
  
  