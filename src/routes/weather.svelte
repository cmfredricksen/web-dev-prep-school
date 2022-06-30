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

<h1>Ely MN Weather Forecast</h1>
I fetched the data from the api using the load function and returned the props weather.

In using this api, I expanded my props down to the main array called periods. And then I used the #each loop in Svelte to unpack periods into name, temperature, etc.

Data is returned as weather.
periods = weather.properties.periods.

<div class="weather-box">
   <div class="weather-periods">
       {#each periods as {name, temperature, windSpeed, windDirection, icon, shortForecast}}
       <p>{name}</p>
       <h2>{temperature}&deg;f</h2>
       <p>{windSpeed} {windDirection}</p>
       <img src={icon} alt="weather icon">
       <p>{shortForecast}</p>
       {/each}
    </div> 
</div>

<style>
    .weather-box {
        display: flex;
        flex-wrap: wrap;
    }
    .weather-periods {
        display: flex;
        flex-direction: column;
    }
    p {
        text-align: center;
    }
    img {
        margin: 0 auto;
    }
</style>