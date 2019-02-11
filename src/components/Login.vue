<template>
<v-card>
    <v-card-text>
        <p class="text-xs-center title font-weight-bold">UniNote</p>
        <v-tabs 
            centered
            v-model="active"
            slider-color="primary"
            >
            <v-tab :key="signin">
                Sign In
            </v-tab>
            <v-tab-item :key="signin">
            <v-card flat>
                <v-card-text>
                    <v-form 
                        ref="form"
                        v-model="valid"
                        lazy-validation
                    >
                        <v-text-field
                            prepend-icon="alternate_email"
                            v-model="email"
                            label="E-Mail"
                            required
                        ></v-text-field>
                        <v-text-field
                            prepend-icon="lock"
                            v-model="password"
                            :append-icon="showPassword ? 'visibility_off' : 'visibility'"
                            :type="showPassword ? 'text' : 'password'"
                            label="Password"
                            @click:append="showPassword = !showPassword"
                            required
                        ></v-text-field>
                        <v-btn @click="submit" color="primary">Sign-In</v-btn>
                    </v-form>
                </v-card-text>
            </v-card>
            </v-tab-item>
            <v-tab :key="signup">
                Sign up
            </v-tab>
            <v-tab-item :key="signup">
                <v-card flat>
                    <v-card-text>
                        <v-form 
                        ref="form"
                        v-model="valid"
                        lazy-validation
                        >
                            <v-text-field
                                v-model="name"
                                label="First Name"
                                required
                            ></v-text-field>
                            <v-text-field
                                v-model="name"
                                label="Last Name"
                                required
                            ></v-text-field>
                            <v-text-field
                                v-model="email"
                                label="E-mail"
                                required
                            ></v-text-field>
                            <v-text-field
                                v-model="password"
                                :append-icon="showPassword ? 'visibility_off' : 'visibility'"
                                :type="showPassword ? 'text' : 'password'"
                                label="Password"
                                @click:append="showPassword = !showPassword"
                                required
                            ></v-text-field>
                            <v-btn @click="submit" color="primary">Sign-Up</v-btn>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-tab-item>
        </v-tabs>
    </v-card-text>
</v-card>
</template>

<script>
export default {
  name: 'login-component',
  data() {
      return {
        showPassword: false
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.panel{
    margin: 0 auto;
    padding: 30px;
    width: 30%;
    background-color: #FFF;
}

.title {
    text-align: center;
}

button {
    width: 100%;
}

.forgot {
    margin-top: 10px;
    text-align: right;
}
</style>
