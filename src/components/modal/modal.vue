<template>
    <transition name="slide-fade">
        <div>
            <div class="mask">
                <div class="m-modal">
                    <div class="headline">
                        <div class="title">
                            <slot name="title"></slot>
                        </div>
                        <div class="m-cancel">
                            <slot name="cancel"></slot>
                        </div>
                    </div>
                    <div class="m-body">
                        <slot name="body"></slot>
                    </div>
                    <div class="m-footer">
                        <slot name="footer"></slot>
                    </div>
                </div>
                <span></span>
            </div>
        </div>
    </transition>
</template>
<script>
export default {
    name: "m-modal"
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
.slide-fade-leave-to {
    transform: translatex(-50px);
    opacity: 0;
}

.headline {
    width: 100%;
    overflow: hidden;
}

.m-cancel {
    width: 60px;
    height: 30px;
    float: right;
}
</style>
