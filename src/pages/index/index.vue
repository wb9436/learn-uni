<template>
    <view class="content">
        <image class="logo" v-bind:src="logoPng"></image>
        <view>
            <text class="title">{{title}}</text>
        </view>
        <view>
            <text class="title" @tap="pop" @touchstart="touchStart">{{loadTime}}</text>
        </view>
        <view>
            <picker @change="bindPickerChange" :value="index" :range="array">
                <view class="picker">
                    当前选择：{{array[index]}}
                </view>
            </picker>
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
                title: 'Hello',
                index: 0,
                array: ['A', 'B', 'C']
            }
        },
        onLoad() {

        },
        computed: {
            loadTime: () => {
                return DateUtil.dateFormat(new Date())
            }
        },
        methods: {
            pop: () => {
                alert('Hello world !!!')
            },
            touchStart: () => {
                console.log('touch start')
            },
            bindPickerChange (e) {
                this.index = e.detail.value
                console.log(e.detail.value)
            }
        }
    }
</script>

<style scoped lang="scss">
    @import "./index";
</style>
