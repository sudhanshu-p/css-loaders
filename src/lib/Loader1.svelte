<script>
    export let detail;
    export let border = 16;
    export let time = 1;
</script>

<div
    class="custom-loader"
    style="border-width: {border}px;
        border-color: {detail
        ? `rgba(${detail.r}, ${detail.g}, ${detail.b}, ${detail.a}) #0000`
        : '#766df4 #0000'};
        animation-duration: {time}s"
/>

<style>
    .custom-loader {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        border-style: solid;
        border-width: 16px;
        border-color: '#766df4 #0000';
        animation: s1 1s infinite;
    }
</style>
