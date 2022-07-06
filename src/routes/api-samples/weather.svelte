<script context="module">
    export const load = async({fetch}) => {
        const res = await fetch("https://api.weather.gov/gridpoints/DLH/98,123/forecast")
        const weather = await res.json();

        return {
            props: {
                weather
            }
        }
    }
</script>

<script>
    export let weather;
    export let periods = weather.properties.periods;
</script>

<h2>Ely MN Weather Forecast</h2>
<p>The local weather forecast for Ely Minnesota which I fetched from <a href="https://api.weather.gov">weather.gov</a>. I had to figure out my grid points first, which tells location. The National Weather Services API is free to use. Below I will show the code I used to fetch, load and then display the data. Click <a href="#results">here</a> to see results</p>

<h3>First you have to fetch and load the data. There are a few things to keep in mind:</h3>
<ul>
    <li>You will have two seperate script blocks.</li>
    <li>The first block needs to be set with context="module".</li>
    <li>You will use the load function which utilizes async/await.</li>
    <li>Return props, which you will use in the second script block</li>
</ul>

<h3>Part 1 Example Below</h3>

<img class="code-pic" src="../../../static/images/code-fetch.png" alt="code snapshot">

<h3>Next you make a second script block right below the first one. Then you export your prop(s) and assign the data to a new variable.</h3>

<h3>Part 2 Example Below</h3>

<img class="code-pic" src="../../../static/images/code-fetch-2.png" alt="code snapshot">

<h3>
    In using this api, I expanded my props down to the main array called periods. And then I used the #each loop in Svelte to unpack periods into name, temperature, etc.
</h3>

<h3>HTML Showing the Data</h3>

<img class="code-pic" src="../../../static/images/weather-box.png" alt="code snapshot">

<h2 id="results">Results with a little css...</h2>
<div class="weather-box">
    {#each periods as {name, temperature, windSpeed, windDirection, icon, shortForecast}}
    <div class="weather-periods">
       <p>{name}</p>
       <h2>{temperature}&deg;f</h2>
       <p>{windSpeed} {windDirection}</p>
       <img src={icon} alt="weather icon">
       <p>{shortForecast}</p>
    </div> 
       {/each}
</div>
<a href="http://localhost:3000/api-samples">Back to List</a>

<style>
    .weather-box {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        margin: 2rem 0;

    }
    .weather-periods {
        display: flex;
        flex-direction: column;
        width: 20%;
        border: 1px solid var(--clr-white);
        border-radius: 1rem;
        outline: 2px solid var(--color-dark);
        background: var(--clr-accent);
        margin: .5rem;
    }

    .code-pic {
        width: 70%;
        margin: 2rem auto;
        border: none;
    }

    li {
        margin: .5rem 0;
        padding: 0;
    }

    p, h2 {
        text-align: center;
    }

    img {
        margin: 0 auto;
        border: 5px solid var(--clr-white-fade);
    }
</style>