<script lang="ts">
    interface IProps {
        allRightsReserved?: boolean;
        someRightsReserved?: boolean;
        noRightsReserved?: boolean;
        ownerName?: string;
        startingYear?: number;
        endYear?: number;
    }

    let {
        allRightsReserved = false,
        someRightsReserved = false,
        noRightsReserved = false,
        ownerName,
        startingYear,
        endYear,
    }: IProps = $props();

    const year: number = endYear || new Date().getFullYear();

    if (startingYear && startingYear > year) {
        throw new Error("Starting year cannot be in the future");
    }

    let text = $state("");

    text += `©${startingYear && startingYear < year ? `${startingYear}-` : ""}${year} ${ownerName}`;

    if (allRightsReserved) {
        text += " All rights reserved";
    }

    if (someRightsReserved) {
        text += " Some rights reserved";
    }

    if (noRightsReserved) {
        text += " No rights reserved";
    }
</script>

<p>
    {text}
</p>

<style>
    p {
        margin: var(--copyright-margin, 0);
        padding: var(--copyright-padding, 0);
        font-size: var(--copyright-font-size, 1rem);
        font-weight: var(--copyright-font-weight, 400);
        font-family: var(--copyright-font-family, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif);
        color: var(--copyright-color, oklch(0, 0, 0));
        line-height: var(--copyright-line-height, 1.2rem);
    }
</style>