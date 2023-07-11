<template>
    <header class="f-header">
        <div class="narrow-container fluid" style="display: flex; align-items: center;">
            <router-link to="/" class="logo" :aria-label="$t('view_home.back_to_home')">
                <img src="logo.png" alt="" class="not-fluid" />
            </router-link>
        </div>
    </header>
</template>

<script>
/**
 * Renderes header and takes care of navigation.
 */
export default {
    components: {},
};
</script>

<style lang="scss">
@import 'style';
</style>
