<template>
    <button class="btn btn-primary w-36 h-20">New counter</button>
    <div class="card text-center" style="width: 18rem;"> 
        <div class="card-body">
            <h4 class="card-title">
                <span class="badge rounded-pill bg-primary">{{ counter }}</span>
            </h4>
            <p class="card-text">Counter: {{ counter_name }}</p>
            <button class="btn btn-danger mx-3 w-12" @click="oneLess">-1</button>
            <button class="btn btn-success mx-3 w-12" @click="oneMore">+1</button>
        </div>
    </div>
</template>
    
<script lang="ts">
import { defineComponent, type Ref, ref } from 'vue';

export default defineComponent({
    name: 'CounterView',
    components: {

    },
    props: {

    },
    methods: {
        oneMore() {
            this.counter += 1
            console.log("¡Se suma 1!", this.counter)
        },
        oneLess() {
            this.counter -= 1
            console.log("¡Se resta 1!", this.counter)
        }
    },
    setup() {
        class Counter {
            amount: number
            counter_name: string

            constructor(amount: number) {
                this.amount = amount
                this.counter_name = this.counter_name
            }

            oneMore() {
                this.counter += 1
                console.log(`Contador ${this.counter_name} suma 1`, this.counter)
            }
            oneLess() {
                this.counter += 1
                console.log(`Contador ${this.counter_name} resta 1`, this.counter)
            }
        }

        const counter: Ref<Number> = ref(0)

        return {
            counter
        }
    }
});
</script>