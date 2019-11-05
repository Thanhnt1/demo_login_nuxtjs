<template>
    <v-app id="login">
        <v-content>
            <v-container fluid fill-height>
                <v-layout align-center justify-center>
                    <v-flex xs12 sm8 md4 lg4>
                        <v-card class="elevation-1 pa-4">
                            <v-card-text >
                                <div class="layout column align-center">
                                    <img src="~/static/images/logo.png" alt="Vue Material Admin" width="120">
                                    <!-- <v-img ></v-img> -->
                                    <h1 class="flex my-4 primary--text">Material Admin Template</h1>
                                </div>
                                <v-form>
                                    <v-text-field
                                        name="login"
                                        label="Login"
                                        type="text"
                                        v-model="userEmail"
                                        append-icon="mdi-account"
                                        :error="error"
                                        :rules="[rules.required]"/>
                                    <v-text-field
                                    :type="hidePassword ? 'password' : 'text'"
                                    append-icon="mdi-lock"
                                    name="password"
                                    label="Password"
                                    id="password"
                                    :rules="[rules.required]"
                                    v-model="password"
                                    :error="error"
                                    @click:append="hidePassword = !hidePassword"/>
                                </v-form>
                            </v-card-text>
                            <v-card-actions>
                                <v-row justify-center>
                                    <v-col cols="12" md="8" sm="6">
                                        <v-btn class="rmv-bd elevation-0">
                                            <v-icon class="fb-icon">mdi-facebook-box</v-icon>
                                        </v-btn>
                                        <v-btn class="rmv-bd elevation-0">
                                            <v-icon class="gg-icon">mdi-google</v-icon>
                                        </v-btn>
                                        <v-btn class="rmv-bd elevation-0">
                                            <v-icon class="twitter-icon">mdi-twitter</v-icon>
                                        </v-btn>
                                    </v-col>
                                    <v-col cols="12" md="4" sm="6">
                                        <v-btn block color="primary" @click="login" :loading="loading">Login</v-btn>
                                    </v-col>
                                </v-row>
                            </v-card-actions>
                        </v-card>
                    </v-flex>
                </v-layout>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>

export default {
    data() {
        return {
        loading: false,
        userEmail: 'admin@example.com',
        password: '123456',
        hidePassword: true,
        error: false,
        showResult: false,
        result: '',
        rules: {
            required: value => !!value || 'Required.'
        }
        }
    },

    methods: {
    },
}
</script>

<style scoped lang="css">
    
    #login {
        height: 50%;
        width: 100%;
        position: absolute;
        top: 0;
        left: 0;
        content: "";
        z-index: 0;
        background-color: #1976d2
    }
    h1 {
        font-family: 'Roboto', sans-serif;
        font-weight: 100;
        font-size: 48px;
        line-height: 1.5;
        box-sizing: inherit;
    }
    
    .rmv-bd {
        padding: 0 !important;
        border: none !important;
        background: none !important;
        border-radius: 50% !important;
        margin: 0 !important;
    }
    .fb-icon {
        color: #2196f3 !important
    }
    .gg-icon {
        color: #f44336 !important;
    }
    .twitter-icon {
        color: #03a9f4 !important;
    }
</style>
