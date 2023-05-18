

## Random Jokes

Here is a joke

<button onclick="getRandomJoke()">Get Another Joke</button>

<div id="joke-container"></div>

<script>
  function getRandomJoke() {
    fetch('https://official-joke-api.appspot.com/random_joke')
      .then(response => response.json())
      .then(data => {
        const setup = data.setup;
        const punchline = data.punchline;
        const jokeElement = document.createElement('div');
        jokeElement.innerHTML = `
          <h3>${setup}</h3>
          <p>${punchline}</p>
        `;
        const jokeContainer = document.getElementById('joke-container');
        jokeContainer.innerHTML = '';
        jokeContainer.appendChild(jokeElement);
      })
      .catch(error => {
        console.log('Error fetching joke:', error);
      });
  }
</script>


---

E
