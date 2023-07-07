# Vue 3 Script Setup Cheat Sheet

## Methods

```javascript
<script setup>
    function getParam(param) {
    return param;
}
</script>

<template>
    {{getParam(1)}}
</template>

```

## Reactive data declaration

```javascript
import {ref, reactive} from 'vue'

const count = ref(0);
const enabled = ref(true)
const object = reactive({variable: false})


if (enabled.value) {
    //
}

const increaseCount = () => {
    count.value++;
};

```

## Computed value

```javascript
import {computed} from "vue";

const count = 0;
const isEmpty = computed(() => {
    return count === 0;
});
```

## Watcher

```javascript
import {watch, ref} from "vue";

const counter = ref(0);
watch(counter, () => {
    console.log("Counter value changed");
});

watch(count, (newValue, oldValue) => {
    console.log('Count changed:', newValue, oldValue);
});
```

## Lifecycle Hooks

```javascript
import {onMounted, onUnmounted} from "vue";

console.log("Equivalent to created hook");
onMounted(() => {
    console.log("Mounted hook called");
});

onUnmounted(() => {
    console.log("Unmounted hook called");
});

```

## Define emits

```javascript
const emit = defineEmits(["event-name"]);

function emitEvent() {
    emit("event-name");
}
```

## Define props

```javascript
defineProps({
    elements: Array,
    counter: {
        type: Number,
        default: 0,
        required: true,
    },
});
```
