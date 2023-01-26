<script>
    // @ts-nocheck

    import Loader1 from "./Loader1.svelte";
    import Modal from "./Modal.svelte";

    let isOpenModal = false;
    let number = 0;
    let r, g, b, a;

    function openModal(index) {
        console.log("Hello");
        isOpenModal = true;
        number = index;
    }

    function closeModal() {
        isOpenModal = false;
    }

    function applyColor(detail) {
        r = detail.r;
        g = detail.g;
        b = detail.b;
        a = detail.a;
    }
</script>

<div class="body">
    <form>
        <input type="text" placeholder="Search..." />
        <button type="submit">Search</button>
    </form>

    <div class="container">
        {#each Array(9) as _, index (index)}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <span class="box" on:click={() => openModal(index)}>
                <Loader1 />
            </span>
        {/each}
    </div>
    <Modal {isOpenModal} on:closeModal={closeModal} />
</div>

<style>
    form {
        text-align: center;
        margin: 15px;
    }
    form input {
        padding: 5px;
        margin-right: 5px;
        border: 2px solid black;
        background-color: rgb(252, 250, 250);
        width: 30vw;
        border-radius: 8px;
    }
    form button {
        background-color: #333;
        color: #fff;
        border: 1px solid rgb(14, 13, 13);
        padding: 5px;
        border-radius: 8px;
        cursor: pointer;
    }
    .container {
        background-color: #0b0f1f;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        flex-direction: row;
    }
    .container .box:hover {
        width: 29%;
        height: 210px;
        background-color: rgb(185, 252, 251);
    }
    .box {
        display: flex;
        width: 27%;
        justify-content: center;
        align-items: center;
        height: 200px;
        border: 2px solid rgb(137, 137, 242);
        background-color: rgb(222, 244, 248);
        margin: 10px;
        text-align: center;
        color: rgb(21, 21, 21);
        border-radius: 7px;
    }
    .body {
        background-color: #0b0f1f;
        height: 100vh;
        padding-top: 5rem;
    }
</style>
