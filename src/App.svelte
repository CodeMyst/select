<script lang="ts">
    import Select from "./Select.svelte";

    const countriesPromise: Promise<[String, String][]> = getCountries();

    async function getCountries() : Promise<[String, String][]> {
        let res: [String, String][] = new Array();

        const apiRes = await fetch("https://restcountries.eu/rest/v2/all");

        const countries = await apiRes.json();

        for (let i = 0; i < countries.length; i++) {
            res.push([countries[i].alpha2Code, countries[i].name]);
        }

        return res;
    }
</script>

<main>
    {#await countriesPromise}
        <span>Loading countries...</span>
    {:then countries}
        <Select label="Country" options={countries} />
    {/await}
</main>

<style>
</style>
