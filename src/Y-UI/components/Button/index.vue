<template>
    <button :disabled="props.disabled"
        :class="`${props.disabled && 'y-button-disabled'} ${!props.disabled && 'y-button'} ${!props.disabled && getButtonType(props.type)} ${getButtonSize(props.size)}`">
        <span>
            <slot></slot>
        </span>
    </button>
</template>

<script setup lang="ts">
const props = defineProps({
    type: {
        type: String,
        default: () => ''
    },
    size: {
        type: String,
        default: () => 'default'
    },
    disabled: {
        tpye: Boolean,
        default: () => false
    }
})
const getButtonType = (type) => {
    switch (type) {
        case 'primary':
            return 'button-primary'
        case 'success':
            return 'button-success'
        case 'danger':
            return 'button-danger'
        case 'warning':
            return 'button-warning'
        case 'info':
            return 'button-info'
        default:
            return ''
    }
}


const getButtonSize = (size) => {
    switch (size) {
        case 'small':
            return 'size-small'
        case 'default':
            return 'size-default'
        case 'large':
            return 'size-large'
        default:
            return 'size-default'
    }
}
</script>

<style scoped lang="scss">
button {
    position: relative;
    margin-right: 8px;
    display: inline-block;
    font-weight: 400;
    white-space: nowrap;
    text-align: center;
    background-image: none;
    border: 1px solid transparent;
    box-shadow: 0 2px #00000004;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    user-select: none;
    touch-action: manipulation;
    border-radius: 2px;
}

.y-button {
    color: #000000d9;
    border-color: #d9d9d9;
    background: #fff;
}

.y-button-disabled {
    color: #0000003e;
    border-color: #d9d9d9;
    background: #eeeeee;
    text-shadow: none;
    box-shadow: none;
    cursor: not-allowed;
}

.y-button:hover {
    color: #1890ff;
    border-color: #1890ff;
}

.y-button:active {
    top: -1px;
    background-color: #188fff18;
}

.button-primary {
    border-color: #409eff;
    background-color: #409eff;
    color: #ffff;
}

.button-primary:hover {
    color: #fff;
    border-color: #1890ff;
}

.button-primary:active {
    border-color: #188fff00;
    background-color: #188fffae;
}

.button-success {
    background-color: #67c23a;
    border-color: #67c23a;
    color: #fff;
}

.button-success:hover {
    color: #fff;
    border-color: #67c23a;
}

.button-success:active {
    border-color: #67c23a00;
    background-color: #67c23ad6;
}

.button-warning {
    background-color: #e6a23c;
    border-color: #e6a23c;
    color: #fff;
}

.button-warning:hover {
    color: #fff;
    border-color: #e6a23c;
}

.button-warning:active {
    border-color: #e6a23c00;
    background-color: #e6a23cbe;
}

.button-danger {
    background-color: #ff4d4f;
    color: #ffff;
    border-color: #ff4d4f;
}

.button-danger:hover {
    color: #fff;
    border-color: #ff4d4f;
}

.button-danger:active {
    border-color: #ff4d5000;
    background-color: #ff4d50b7;
}

.button-info {
    background-color: #909399;
    border-color: #909399;
    color: #fff;
}

.button-info:hover {
    color: #fff;
    border-color: #909399;
}

.button-info:active {
    border-color: #90939900;
    background-color: #909399b0;
}

.size-small {
    padding: 2px 8px;
    font-size: 12px;
}

.size-default {
    height: 28px;
    padding: 4px 11px;
    font-size: 12px;
}

.size-large {
    height: 32px;
    padding: 4px 14px;
    font-size: 13px;
}
</style>