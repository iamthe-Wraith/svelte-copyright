<script lang="ts">
    interface IProps {
        allRightsReserved?: boolean;
        companyName?: string;
        companyNamePosition?: 'start' | 'end';
        startingYear?: number;
        endYear?: number;
    }

    let {
        allRightsReserved = false,
        companyName,
        companyNamePosition = 'end',
        startingYear,
        endYear,
    }: IProps = $props();

    const year: number = endYear || new Date().getFullYear();

    if (startingYear && startingYear > year) {
        throw new Error("Starting year cannot be in the future");
    }

    let text = $state("");

    if (companyNamePosition === 'start' && companyName) {
        text += `${companyName} `;
    }

    text += `©${startingYear && startingYear < year ? `${startingYear}-` : ""}${year}`;

    if (companyNamePosition === 'end' && companyName) {
        text += ` ${companyName}`;
    }

    if (allRightsReserved) {
        text += " All rights reserved";
    }
</script>

<p>
    {text}
</p>

<style>
    p {
        margin: var(--margin, 0);
        padding: var(--padding, 0);
        font-size: var(--font-size, 1rem);
        font-weight: var(--font-weight, 400);
        font-family: var(--font-family, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif);
        color: var(--copyright-color, oklch(0, 0, 0));
        line-height: var(--line-height, 1.5);
    }
</style>