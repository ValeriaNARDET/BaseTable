<template>
  <div class="container">
    <h1 class="title">
      Test task
    </h1>
    <h2 class="subtitle">
      Using base table component
    </h2>
    <ul>
      <li>
        <nuxt-link class='link' to='/comments'>Table with users' comments</nuxt-link>
      </li>
      <li>
        <nuxt-link class='link' to='/users'>Users table</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {}
</script>

<style>
.container {
  margin: 0 auto;
  padding: 40px;
  min-height: 100vh;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-weight: 300;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
  text-align: center;
}

.subtitle {
  font-weight: 300;
  font-size: 32px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 35px;
  text-align: center;
}

.link {
  font-size: 20px;
  line-height: 40px;
  text-decoration: none;
  transition: all 0.3s;
}

.link:hover {
  text-decoration: underline;
}

.back-btn {
    margin: 20px 0;
    padding: 10px 40px;
    border: 1px solid #07a02d;
    border-radius: 18px;
    font-size: 16px;
    font-weight: bold;
    color: #07a02d;
    background-color: #e5fbda;
  transition: all 0.3s;
}

.back-btn:hover {
  box-shadow: 2px 3px 5px #ececec;
}
</style>
