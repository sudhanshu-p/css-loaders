<script>
    import { createEventDispatcher } from "svelte";
    import Loader1 from "./Loader1.svelte";
    import { HsvPicker } from "svelte-color-picker";
    import Paint from "../assets/paint-pallete.png";
    import Size from "../assets/loader-size.png";
    import Speed from "../assets/loader-speed.png";
    import { HighlightSvelte } from "svelte-highlight";
    import atomOneDark from "svelte-highlight/styles/atom-one-dark";
    import css from "svelte-highlight/languages/css";

    const dispatch = createEventDispatcher();
    let stateOfModal = "customize";
    let isColorOpen = false;
    let detail = {
        r: 3,
        g: 99,
        b: 255,
        a: 1,
    };
    let border = 16;
    let time = 1;
    const htmlCode = `<div class="custom-loader"></div>`;
    $: cssCode = `.custom-loader {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border-style: solid;
    border-width: ${border}px;
    border-color: rgba(${detail.r}, ${detail.g}, ${detail.b}, ${detail.a}) #0000;
    animation: s1 ${time}s infinite;
}
@keyframes s1 {
    to {
        transform: rotate(0.5turn);
    }
}
    `;
    export let isOpenModal;

    function closeModal() {
        isOpenModal = false;
        dispatch("closeModal", { isOpenModal });
    }

    function applyColorToModal(rgba) {
        detail = rgba.detail;
    }
</script>

<svelte:head>
    {@html atomOneDark}
</svelte:head>

<div
    id="background"
    style="--display: {isOpenModal ? 'block' : 'none'};"
    on:click={closeModal}
/>

<div
    id="background-2"
    style="--display: {isColorOpen ? 'block' : 'none'};"
    on:click={() => (isColorOpen = false)}
/>

<div id="modal" style="--display: {isOpenModal ? 'block' : 'none'};">
    <div class="modal-head">
        <button
            class="customize"
            style="background-color: {stateOfModal === 'customize'
                ? '#0363ff'
                : 'transparent'}"
            on:click={() => (stateOfModal = "customize")}>Customize</button
        >
        <button
            class="get-code"
            style="background-color: {stateOfModal === 'get-code'
                ? '#0363ff'
                : 'transparent'}"
            on:click={() => (stateOfModal = "get-code")}>Get Code</button
        >
    </div>
    <div class="modal-body">
        <div class="modal-left">
            {#if stateOfModal === "customize"}
                <Loader1 {detail} {border} {time} />
            {/if}
        </div>
        <div class="modal-right">
            {#if stateOfModal === "customize"}
                <span class="color-select">
                    <img src={Paint} alt="" />
                    <h2>Primary Color:</h2>
                    <span class="color-picker">
                        {#if isColorOpen}
                            <HsvPicker
                                on:colorChange={applyColorToModal}
                                startColor={"#FBFBFB"}
                            />
                            <button on:click={() => (isColorOpen = false)}>
                                Okay
                            </button>
                        {:else}
                            <button on:click={() => (isColorOpen = true)}
                                >Select</button
                            >
                        {/if}
                    </span>
                </span>
                <span class="boundary-select">
                    <img src={Size} alt="" />
                    <h2>Loader Size</h2>
                    <input type="range" bind:value={border} min="0" max="25" />
                </span>
                <span class="time-select">
                    <img src={Speed} alt="" />
                    <h2>Loader Speed</h2>
                    <input
                        type="range"
                        bind:value={time}
                        min="0.5"
                        max="2"
                        step="0.1"
                    />
                </span>
            {:else}
                <h4>HTML:</h4>
                <div class="code">
                    <HighlightSvelte code={htmlCode} class="high-code" />
                </div>
                <h4>CSS:</h4>
                <div class="code">
                    <HighlightSvelte code={cssCode} language={css} />
                </div>
            {/if}
        </div>
    </div>
</div>

<style>
    .color-select,
    .boundary-select,
    .time-select {
        display: flex;
        gap: 2rem;
        justify-content: left;
        align-items: center;
        align-content: left;
    }

    .modal-right {
        overflow-x: auto;
    }

    @media screen and (max-width: 992px) {
        .color-select,
        .boundary-select,
        .time-select {
            flex-direction: column;
        }
    }

    .color-picker > button {
        background-color: #0363ff;
        padding: 1rem;
        border: none;
        color: white;
        border-radius: 0.5rem;
    }

    #background {
        display: var(--display);
        position: fixed;
        z-index: 1;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
    }

    #background-2 {
        display: var(--display);
        position: fixed;
        z-index: 1;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
    }

    #modal {
        display: var(--display);
        position: fixed;
        z-index: 2;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background: white;
        color: black;
        filter: drop-shadow(0 0 20px #333);
        width: min(80%, 50rem);
        margin-top: 2rem;
        z-index: 1000;
    }
    #modal > * {
        padding: 20px;
    }

    .modal-head {
        margin: 5%;
        background-color: #d9d9d9;
        width: 90%;
        display: flex;
    }
    .modal-head > button {
        font-weight: bolder;
        font-size: 1.5rem;
    }

    .customize,
    .get-code {
        min-width: 50%;
        padding: 5%;
        text-align: center;
        border: none;
        border-radius: 0.3rem;
    }
    .modal-body {
        margin: 5%;
        width: 90%;
        display: flex;
        gap: 2rem;
    }
    .modal-right {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        padding-left: 1rem;
        align-content: flex-start;
    }
    .modal-left {
        border-radius: 0.3rem;
        box-shadow: #333;
    }
</style>
