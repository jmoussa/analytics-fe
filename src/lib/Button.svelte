<script>
    import { createEventDispatcher } from 'svelte';
    import '../app.css';

    export let label = '';
    export let classes = ['btn btn-primary'];

    const dispatch = createEventDispatcher();
     /**
     * Button click handler
     */
    function onClickDefault(event) {
      dispatch('click', event);
    }
    export let onClick = onClickDefault;    

</script>

<button
    type="button"
    class={classes.join(' ')}
    on:click={onClick}>
    {label}
</button>

<style scoped>
.sveltio-button {
    font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
    font-weight: 700;
    border: 0;
    border-radius: 3px;
    cursor: pointer;
    display: inline-block;
    line-height: 1;
}
.sveltio-button--primary {
    color: #1b116e;
    background-color: #6bedb5;
}
.sveltio-button--secondary {
    color: #ffffff;
    background-color: #1b116e;
    box-shadow: rgba(0, 0, 0, 0.15) 0px 0px 0px 1px inset;
}
.sveltio-button--small {
    font-size: 12px;
    padding: 10px 16px;
}
.sveltio-button--medium {
    font-size: 14px;
    padding: 11px 20px;
}
.sveltio-button--large {
    font-size: 16px;
    padding: 12px 24px;
}

button:hover {
    color: #1b116e;
    background-color: #55bd90;
}

button:active {
    color: #1b116e;
    background-color: #55bd90;
    border: solid 2px #1b116e;
}

button:disabled {
    color: #1b116e;
    opacity: 0.5;
    background-color: #6bedb5;
}

button:hover {
    color: #1b116e;
    background-color: #55bd90;
}

button:active {
    color: #1b116e;
    background-color: #6bedb5;
    border: solid 2px #1b116e;
}

button:disabled {
    color: #ffffff;
    opacity: 0.5;
    background-color: #1b116e;
}

</style>