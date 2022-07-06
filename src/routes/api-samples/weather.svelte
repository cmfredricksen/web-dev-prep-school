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
I fetched the data from the api using the load function and returned the props weather.

In using this api, I expanded my props down to the main array called periods. And then I used the #each loop in Svelte to unpack periods into name, temperature, etc.

Data is returned as weather.
periods = weather.properties.periods.

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
        justify-content: center;
        margin: 2rem 0;

    }
    .weather-periods {
        display: flex;
        flex-direction: column;
        width: 20%;
        border: 1px solid var(--clr-white);
        background: var(--clr-accent);
        margin: .5rem;
    }

    

    p, h2 {
        text-align: center;
    }
    img {
        margin: 0 auto;
        border: 5px solid var(--clr-white-fade);
    }
</style>