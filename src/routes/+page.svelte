<script lang="ts">
    import Copyright from "$lib/Copyright.svelte";
</script>

<div class="examples-container">
    <Copyright />
    <Copyright startingYear={2022} />
    <Copyright companyName="Stark Industries" />
    <Copyright companyName="Stark Industries" companyNamePosition="start" />
    <Copyright companyName="Stark Industries" startingYear={2022} allRightsReserved />
    <Copyright companyName="Stark Industries" startingYear={2022} allRightsReserved companyNamePosition="start" />
    <Copyright companyName="Stark Industries" startingYear={2022} endYear={2024} allRightsReserved companyNamePosition="start" />
    <Copyright companyName="Stark Industries" startingYear={2022} endYear={2024} allRightsReserved companyNamePosition="end" />
</div>

<style>
    .examples-container {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
</style>