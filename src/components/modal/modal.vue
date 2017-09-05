<template>
    <div class="mask">
        <div class="m-modal">
            <div class="headline">
                <div class="title">
                    <b>
                        <slot name="title"></slot>
                    </b>
                </div>
                <button class="delete">
                    <slot name="delete"></slot>
                </button>
            </div>
            <div class="body">
                <slot name="body"></slot>
            </div>
            <div class="footer">
                <button class="btn cancel">
                    <slot name="cancel"></slot>
                </button>
                <button class="btn confirm">
                    <slot name="confirm"></slot>
                </button>
            </div>
        </div>
    </div>
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
    padding: 20px;
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
    height: 20px;
}

.title {
    display: inline-block;
    font-size: 16px;
    line-height: 20px;
    vertical-align: top;
}

.delete {
    width: 30px;
    height: 20px;
    float: right;
    background-color: transparent;
    color: #dcdcdc;
    font-size: 20px;
}

.delete:hover {
    color: $primary-darker;
}

.body {
    padding-top: 20px;
    height: 120px;
    font-size: 16px;
}

.footer {
    float: right;
}

.btn {
    width: 60px;
    height: 36px;
    border-radius: 4px;
}

.cancel {
    background-color: transparent;
    color: #000;
    border: 1px solid #dcdcdc;
}

.cancel:hover {
    color: $primary-darker;
    border: 1px solid $primary-darker;
}

.confirm {
    background-color: $primary-darker;
    color: #fff;
    margin-left: 20px;
}

.confirm:hover {
    background-color: $primary-middium;
}
</style>
