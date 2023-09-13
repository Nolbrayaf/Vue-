<template>
    <button>
        <slot />
    </button>
</template>


<style scoped>
button {
    position: relative;
    background-color: white;
    border: 0;
    cursor: pointer;
    border-radius: 5px;
    padding: 10px 15px;
    color: black;
    transition: 0.2s ease-in-out;

}


button:hover {
    background-color: #006e99;
    color: white;
}

button:disabled {
    opacity: 0.5;
}
</style>
