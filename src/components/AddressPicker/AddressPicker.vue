<template>
    <div class="address-picker">
        <template v-if="blockchain === 'skyhigh'">
            <h2>Wallets</h2>
            <account-list pick-mode @account-picked="onAddressPicked" />
        </template>
        <h2>Contacts</h2>
        <contact-list pick-mode :filter-by-blockchain="blockchain" @contact-picked="onAddressPicked" />
    </div>
</template>

<script>
import AccountList from '../AccountList/AccountList.vue';
import ContactList from '../ContactList/ContactList.vue';

export default {
    name: 'AddressPicker',

    components: { ContactList, AccountList },

    props: {
        /** @type {WalletBlockchain} */
        blockchain: {
            type: String,
            default: 'skyhigh',
            validator: function (_value) {
                return ['skyhigh', 'ethereum', 'binance'].indexOf(_value) !== -1;
            },
        },
    },

    methods: {
        onAddressPicked(_address) {
            this.$emit('address-picked', _address);
        },
    },
};
</script>

<style lang="scss">
@import 'style';
</style>
