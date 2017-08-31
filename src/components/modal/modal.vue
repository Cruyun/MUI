<template>
    <transition name="slide-fade">
        <div>
            <div class="mask">
                <div class="m-modal">
                    <slot name="title"></slot>
                    <button class="m-cancel" v-on:click="cancelButton">
                        <slot name="cancel"></slot>
                    </button>
                    <div class="m-body">
                        <slot name="body"></slot>
                    </div>
                    <div class="m-footer">
                        <slot name="footer"></slot>
                    </div>
                </div>
            </div>
        </div>
    </transition>
</template>
<script>
export default {
    name: "m-modal",
    data() {
        return {
            cancelShow: true
        }
    },
    props: {
        visible: {
            type: Boolean,
            default: true
        },
    },
    methods: {
        cancelButton: function() {
            this.cancelShow = false
            console.log(this.cancelShow, "this.cancelShow")
        }
    },
}
</script>
<style lang="scss">
@import '../../scss/common/color.scss';
@import '../../scss/common/font.scss';
.m-modal {
    width: 400px;
    height: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border: 2px solid #dcdcdc;
    background-color: #ffffff;
}

.mask {
    width: 100%;
    height: 100%;
    background-color: rgba(51, 51, 51, 0.3);
    position: absolute;
    top: 0;
    left: 0;
    z-index: 3;
}

.slide-fade-enter-active {
    transition: all .3s ease;
}

.slide-fade-leave-active {
    transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}

.slide-fade-enter,
.slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */

{
    transform: translatex(-50px);
    opacity: 0;
}
</style>
