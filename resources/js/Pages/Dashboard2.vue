<script setup>
import MyLayout from "@/Layouts/MyLayout.vue";
import Menubar from "primevue/menubar";
import Dropdown from "primevue/dropdown";
import Card from "primevue/card";
import Button from 'primevue/button';
import { Head, Link } from "@inertiajs/inertia-vue3";
import { ref } from "vue";
const selectedCity = ref("");
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
            <Dropdown
                v-model="selectedCity"
                :options="cities"
                optionLabel="name"
                placeholder="Select a City"
            />

            <br />
            <Card style="width: 25em">
                <template #header>
                    <img
                        src="https://www.primefaces.org/wp-content/uploads/2020/02/primefacesorg-primevue-2020.png"
                        style="height: 15rem"
                    />
                </template>
                <template #title> Advanced Card </template>
                <template #subtitle> Card subtitle </template>
                <template #content>
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                        Inventore sed consequuntur error repudiandae numquam
                        deserunt quisquam repellat libero asperiores earum nam
                        nobis, culpa ratione quam perferendis esse, cupiditate neque
                        quas!
                    </p>
                </template>
                <template #footer>
                    <Button icon="pi pi-check" label="Save" />
                    <Button
                        icon="pi pi-times"
                        label="Cancel"
                        class="p-button-secondary"
                        style="margin-left: 0.5em"
                    />
                </template>
            </Card>
        </MyLayout>
        
    </div>
</template>
