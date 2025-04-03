<template>
    <Banner><p>привет</p></Banner>

    <div class="layout">
      <div class="left-column">
        <p>Плюсы работы фронтендера</p>
        <ul>
            <li>Творческая реализация</li>
            <li>Высокая востребованность</li>
            <li>Быстрая обратная связь</li>
        </ul>
      </div>

      

      <div class="content">
        <p>Поприветствуйте Егора!</p>
        <img class="img" src="/image/tiger.jpg" alt="">

        <div class="cards-container">
          <Card>UF</Card>
          <Card>UF</Card>
        </div>

        <p>{{ message }}</p>
        <button @click="toggleMessage">Поменять приветствие</button>
      </div>

      <div class="right-column">
        <p>Мечтаю работать в FEIP</p>
      </div>
    </div>
  </template>

  <script setup>
  import { ref } from 'vue'

  const defaultText = 'Привет!'
  const changedText = 'Дарова!'

  const message = ref(defaultText)
  const isChanged = ref(false)

  const toggleMessage = () => {
    isChanged.value = !isChanged.value
    message.value = isChanged.value ? changedText : defaultText
  }
  </script>

  <style scoped lang="scss">
  .layout {
    display: flex;
    height: 100%;
    gap: 20px;

  }

  .left-column,
  .right-column {
    
    width: 20%;
    // height: 300%;
    background-color: #f4f4f4;
    padding: 10px;
    text-align: center;
    // height: 100%;
  }

  .content {
    flex: 1;
    margin: 20px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .img {
    width: 25%;
    min-width: 200px;
    // height: 25%;
    aspect-ratio: 1/1;
  }

  .cards-container {
    display: flex;
    
    gap: 16px;
    margin-top: 20px;
  }
  .content {
  font-family: var(--font-primary);
}

.left-column,
.right-column {
  font-family: var(--font-secondary);
}
  </style>