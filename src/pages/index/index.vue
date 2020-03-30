<template>
    <view class="content">
        <image class="logo" v-bind:src="logoPng"></image>
        <view>
            <text class="title">{{title}}</text>
        </view>
        <view>
            <text class="title">{{loadTime}}</text>
        </view>
    </view>
</template>

<script>
    import LogoPng from '../../static/logo.png'
    import * as DateUtil from '../../utils/dateUtil'

    export default {
        data() {
            return {
                logoPng: LogoPng,
                title: 'Hello'
            }
        },
        onLoad() {

        },
        computed: {
            loadTime: () => {
                return DateUtil.dateFormat(new Date())
            }
        },
        methods: {}
    }
</script>

<style scoped lang="scss">
    @import "./index";
</style>
