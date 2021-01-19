<template>
    <div class="uk-section uk-section-muted uk-flex uk-flex-middle uk-animation-fade" uk-height-viewport>
    <div class="uk-width-1-1">
        <div class="uk-container">
            <div class="uk-grid-margin uk-grid uk-grid-stack" uk-grid>
                <div class="uk-width-1-1@m">
                    <div class="uk-margin uk-width-large uk-margin-auto uk-card uk-card-default uk-card-body uk-box-shadow-large">
                        <h3 class="uk-card-title uk-text-center">Welcome back!</h3>
                        <form>
                            <div class="uk-margin">
                                <div class="uk-inline uk-width-1-1">
                                    <span class="uk-form-icon" uk-icon="icon: mail"></span>
                                    <input v-model="email" class="uk-input uk-form-large" type="text">
                                </div>
                            </div>
                            <div class="uk-margin">
                                <div class="uk-inline uk-width-1-1">
                                    <span class="uk-form-icon" uk-icon="icon: lock"></span>
                                    <input v-model="password" class="uk-input uk-form-large" type="password">
                                </div>
                            </div>
                            <div class="uk-margin">
                                <button class="uk-button uk-button-primary uk-button-large uk-width-1-1">Login</button>
                            </div>
                            <div class="uk-text-small uk-text-center">
                                Not registered? <a href="#">Create an account</a>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
    name: "Login",
    data: () => ({
        form: {
            email: '',
            password: '',
        }
    }),
    methods: {
        getInfo (){
            axios.post('/api/auth/login', this.form)
                .then(function (response) {
                    // handle success
                    console.log(response);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
                .then(function () {
                    // always executed
                });
        }
    }
}
</script>

<style scoped>

</style>
