<script setup>
import MyLayout from "@/Layouts/MyLayout.vue";
import Menubar from 'primevue/menubar';
import Dropdown from "primevue/dropdown";
import { Head, Link } from "@inertiajs/inertia-vue3";
import { ref } from "vue";
const items = [
    {
        label: "Edit",
        icon: "pi pi-fw pi-pencil",
        url: "#",
        items: [
            {
                label: "Left",
                url: "#",
                icon: "pi pi-fw pi-align-left",
            },
            {
                label: "Right",
                url: "#",
                icon: "pi pi-fw pi-align-right",
            },
            {
                label: "Center",
                url: "#",
                icon: "pi pi-fw pi-align-center",
            },
            {
                label: "Justify",
                url: "#",
                icon: "pi pi-fw pi-align-justify",
            },
        ],
    },
];
const selectedCity = ref('')
const cities = [
    { name: "New York", code: "NY" },
    { name: "Rome", code: "RM" },
    { name: "London", code: "LDN" },
    { name: "Istanbul", code: "IST" },
    { name: "Paris", code: "PRS" },
];
</script>

<template>
    <div class="m-6">
        
        <MyLayout>
            <Menubar :model="items">
                <template #start>
                    Before
                </template>
                <template #item="{item}">
                    <!-- <a :href="item.url">{{item.label}}</a> -->
                    <pre>
                        {{item.label}}
                    </pre>
                </template>
                <template #end>
                    After
                </template>
            </Menubar>

            <Dropdown
                v-model="selectedCity"
                :options="cities"
                optionLabel="name"
                placeholder="Select a City"
            />
        </MyLayout>
    </div>
</template>
