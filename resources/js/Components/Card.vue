<script setup>

</script>

<template>
    <div class="">
        <div class="card p-4 py-2">

                <div id="card-header">
                    <slot name="header"></slot>
                <hr>
                </div>
                <div id="card-content">
                    <slot></slot>
                </div>
                <div id="card-content1">
                    <slot name="content1"></slot>
                </div>
                <div id="card-footer">
                    <slot name="footer"></slot>
                </div>

        </div>

    </div>
</template>
