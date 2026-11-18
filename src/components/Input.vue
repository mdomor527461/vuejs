<template>
    <div>
      
      <input
        type="text"
        :value="modelValue"
        placeholder="Type something..." @input="$emit('update:modelValue',$event.target.value)"
        />
        <p>You typed: {{ modelValue  }}</p>
    </div>
</template>

<script setup>

defineProps({
  modelValue: String
})

defineEmits(['update:modelValue'])

</script>