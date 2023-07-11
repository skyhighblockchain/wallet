<template>
    <footer class="f-footer">
        <div class="narrow-container fluid">
            <div class="row align-items-center">
                <div class="col-12 align-center">
                    <social-media-links></social-media-links>
                </div>
                <!-- <div class="col-12 align-center">
                    <a href="https://skyhighblockchain.com/" class="f-footer-text" target="_blank" rel="noopener">©2020 SkyHigh</a>
                </div> -->
            </div>
        </div>
    </footer>
</template>

<script>
import SocialMediaLinks from '../SocialMediaLinks/SocialMediaLinks.vue';

export default {
    components: {
        SocialMediaLinks,
    },
};
</script>

<style lang="scss">
@import 'style';
</style>
