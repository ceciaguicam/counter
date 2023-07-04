<template>
    <div class="card text-center mx-4" style="width: 18rem;">
        <div class="card-body">
            <p class="card-text">New counter</p>
            <div class="input-group mb-3">
                <form>
                    <input type="text" class="form-control" placeholder="Counter name" aria-label="Counter name"
                        aria-describedby="button-addon2" v-model="new_counter_name">
                    <button class="btn btn-outline-secondary" type="button" id="button-addon2" @click="createNewCounter(new_counter_name)">Create</button>
                </form>
            </div>
        </div>
    </div>

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
        },
        createNewCounter(counter_name: string) {
            console.log("Counter name", this.new_counter_name)
            console.log("Entra en función")
            console.log("Nuevo contador", counter_name)
            /* const new_counter = new this.Counter(0, counter_name) */
        }
    },
    setup() {

        const new_counter_name: Ref<string | undefined> = ref()

        class Counter {
            amount: number
            counter_name: string

            constructor(amount: number, counter_name: string) {
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
            counter,
            Counter,
            new_counter_name
        }
    }
});
</script>