<template>
    <div class="calculator">

        <div class="calculator-container">
          <div class="container">
            <div class="row">
              <div class="col-md-12">
                <div class="form-group">
                  <input v-model="result" class="form-control input" type="text" placeholder="0">
                </div>
              </div>
              <div class="col-md-12">
                <div class="form-result">
                  {{ total }}
                </div>
              </div>
              <div class="col-md-12">
                <hr>
              </div>
            </div>
            <div class="row row-buttons">
              <div class="col-9">
                <button @click="clear" class="btn btn-block btn-secondary btn-symbol">C</button>
              </div>
              <div class="col-3">
                <button @click="math('+')" class="btn btn-block btn-secondary btn-symbol">+</button>
              </div>

              <div class="col-3">
                <button @click="number(7)" class="btn btn-block btn-primary btn-number">7</button>
              </div>
              <div class="col-3">
                <button @click="number(8)" class="btn btn-block btn-primary btn-number">8</button>
              </div>
              <div class="col-3">
                <button @click="number(9)" class="btn btn-block btn-primary btn-number">9</button>
              </div>

              <div class="col-3">
                <button @click="math('-')" class="btn btn-block btn-secondary btn-symbol">-</button>
              </div>

              <div class="col-3">
                <button @click="number(4)" class="btn btn-block btn-primary btn-number">4</button>
              </div>
              <div class="col-3">
                <button @click="number(5)" class="btn btn-block btn-primary btn-number">5</button>
              </div>
              <div class="col-3">
                <button @click="number(6)" class="btn btn-block btn-primary btn-number">6</button>
              </div>

              <div class="col-3">
                <button @click="math('*')" class="btn btn-block btn-secondary btn-symbol">*</button>
              </div>

              <div class="col-3">
                <button @click="number(1)" class="btn btn-block btn-primary btn-number">1</button>
              </div>
              <div class="col-3">
                <button @click="number(2)" class="btn btn-block btn-primary btn-number">2</button>
              </div>
              <div class="col-3">
                <button @click="number(3)" class="btn btn-block btn-primary btn-number">3</button>
              </div>

              <div class="col-3">
                <button @click="math('/')" class="btn btn-block btn-secondary btn-symbol">/</button>
              </div>

              <div class="col-3">
                <button @click="number(0)" class="btn btn-block btn-primary btn-number">0</button>
              </div>

              <div class="col-3">
                <button @click="math('.')" class="btn btn-block btn-primary btn-symbol">.</button>
              </div>

              <div class="col-6">
                <button @click="equal" class="btn btn-block btn-secondary">=</button>
              </div>

            </div>
          </div>
        </div>

        <hr>

        <div class="calculator-result container">
            <div class="row">
                <div class="col-md-12">
                    <div v-for="item in items"
                         :key="item"
                         class="card">
                        {{ item.formula }} = {{ item.total }}
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                result: "",
                total: 0,
                items: []
            }
        },
        methods: {
            number(item) {
                this.result += item;
            },
            math(item) {
                this.result += item.toString();
            },
            equal() {
              // TODO add check for start from zero
                this.total = eval(this.result);
                this.items.push({formula: this.result, total: this.total});

                this.clear();
            },
            clear() {
                this.result = "";
            }
        }
    }
</script>

<style>

</style>
