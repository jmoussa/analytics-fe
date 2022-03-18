<script>
    import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
    import Header from "./Header.svelte";
</script>


<Meta
    title="Sveltio/Header"
    component={Header}
/>


<Template let:args>
    <Header {...args} on:click={args.onClick} />
</Template>

<Story
    name="Primary"
    args={{
        primary: true,
        label: "Header",
    }}
/>


<Story
    name="Secondary"
    args={{
        label: "Header",
    }}
/>
<Story
    name="Large"
    args={{
        size: "large",
        label: "Header",
    }}
/>


<Story
    name="Small"
    args={{
        size: "small",
        label: "Header",
    }}
/>