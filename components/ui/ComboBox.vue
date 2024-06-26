<template>
    <div class="w-full my-10">
        <Combobox v-model="selected" @update:modelValue="emitSelected">
            <div class="relative mt-1">
                <div
                    class="relative w-full cursor-default overflow-hidden rounded-lg bg-white text-left shadow-md focus:outline-none focus-visible:ring-2 focus-visible:ring-white/75 focus-visible:ring-offset-2 focus-visible:ring-offset-teal-300 sm:text-sm">
                    <ComboboxInput
                        class="w-full border-none rounded-lg py-3 pl-3 pr-10 text-lg font-family-oswald leading-5 text-gray-900 focus:ring-0 focus-visible:outline-none focus-within:border border-2"
                        :displayValue="(item) => item.name" @change="query = $event.target.value" />
                    <ComboboxButton class="absolute inset-y-0 right-0 flex items-center pr-2">
                        <ChevronUpDownIcon class="h-5 w-5 text-gray-400" aria-hidden="true" />
                    </ComboboxButton>
                </div>
                <TransitionRoot leave="transition ease-in duration-100" leaveFrom="opacity-100" leaveTo="opacity-0"
                    @after-leave="query = ''">
                    <ComboboxOptions
                        class="absolute mt-1 max-h-60 w-full overflow-auto rounded-md bg-white py-1 text-base shadow-lg ring-1 ring-black/5 focus:outline-none sm:text-sm">
                        <div v-if="filteredItems.length === 0 && query !== ''"
                            class="relative cursor-default select-none px-4 py-2 text-gray-700">
                            Bir sonuç bulunmadı
                        </div>

                        <ComboboxOption v-for="item in filteredItems" as="template" :key="item.id" :value="item"
                            v-slot="{ selected, active }">
                            <li class="relative cursor-default select-none py-2 pl-10 pr-4" :class="{
                                'bg-sky-600 text-white': active,
                                'text-gray-900': !active,
                            }">
                                <span class="block truncate" :class="{ 'font-medium': selected, 'font-normal': !selected }">
                                    {{ item.name }}
                                </span>
                                <span v-if="selected" class="absolute inset-y-0 left-0 flex items-center pl-3"
                                    :class="{ 'text-white': active, 'text-sky-600': !active }">
                                    <CheckIcon class="h-5 w-5" aria-hidden="true" />
                                </span>
                            </li>
                        </ComboboxOption>
                    </ComboboxOptions>
                </TransitionRoot>
            </div>
        </Combobox>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import {
    Combobox,
    ComboboxInput,
    ComboboxButton,
    ComboboxOptions,
    ComboboxOption,
    TransitionRoot,
} from '@headlessui/vue'
import { CheckIcon, ChevronUpDownIcon } from '@heroicons/vue/20/solid'

// Define props and emits
const props = defineProps({
    items: {
        type: Array,
        required: true
    }
})
const emit = defineEmits(['update:selectedItem'])

let selected = ref(props.items[0])
let query = ref('')

// Compute the filtered items based on the query
let filteredItems = computed(() =>
    query.value === ''
        ? props.items
        : props.items.filter((item) =>
            item.name
                .toLowerCase()
                .replace(/\s+/g, '')
                .includes(query.value.toLowerCase().replace(/\s+/g, ''))
        )
)

// Emit the selected item when it changes
const emitSelected = (value) => {
    emit('update:selectedItem', value)
}

</script>
