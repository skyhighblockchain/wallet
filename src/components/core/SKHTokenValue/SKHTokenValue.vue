<template>
    <span class="skhtokenvalue">
        <f-token-value
            :value="cValue"
            :decimals="filtersOptions.fractionDigits"
            :number-currency="withPriceCurrency ? filtersOptions.currency : undefined"
            :use-placeholder="false"
            no-currency
            v-bind="$attrs"
        />
        <span v-if="!noCurrency"> SKH</span>
    </span>
</template>

<script>
import FTokenValue from '@/components/core/FTokenValue/FTokenValue.vue';
import { WEIToSKH } from '@/utils/transactions.js';
import { filtersOptions } from '@/filters.js';

export default {
    name: 'SKHTokenValue',

    components: { FTokenValue },

    props: {
        value: {
            type: [String, Number],
            default: 0,
        },
        /** Convert value to SKH */
        convert: {
            type: Boolean,
            default: false,
        },
        noCurrency: {
            type: Boolean,
            default: false,
        },
        withPriceCurrency: {
            type: Boolean,
            default: false,
        },
    },

    data() {
        return {
            filtersOptions,
        };
    },

    computed: {
        cValue() {
            return this.convert ? WEIToSKH(this.value) : this.value;
        },
    },
};
</script>
