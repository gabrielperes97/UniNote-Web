<template>
<v-card>
    <v-card-text>
        <p class="text-xs-center title font-weight-bold">UniNote</p>
        <v-tabs
            centered
            slider-color="primary"
            >
            <v-tab>
                Sign In
            </v-tab>
            <v-tab-item>
            <v-card flat>
                <v-card-text>
                    <v-form>
                        <v-text-field
                            prepend-icon="alternate_email"
                            v-model="email"
                            label="E-Mail"
                            required
                            :error-messages="emailErrors"
                            @input="$v.email.$touch()"
                            @blur="$v.email.$touch()"
                        ></v-text-field>
                        <v-text-field
                            prepend-icon="lock"
                            v-model="password"
                            :append-icon="showPassword ? 'visibility_off' : 'visibility'"
                            :type="showPassword ? 'text' : 'password'"
                            label="Password"
                            @click:append="showPassword = !showPassword"
                            required
                            :error-messages="passErrors"
                            @input="$v.password.$touch()"
                            @blur="$v.password.$touch()"
                        ></v-text-field>
                        <v-btn color="primary">Sign-In</v-btn>
                    </v-form>
                </v-card-text>
            </v-card>
            </v-tab-item>
            <v-tab>
                Sign up
            </v-tab>
            <v-tab-item>
                <v-card flat>
                    <v-card-text>
                        <v-form
                        ref="form-signup"
                        lazy-validation
                        >
                            <v-text-field
                                v-model="firstName"
                                label="First Name"
                                required
                                :error-messages="firstNameErrors"
                                @input="$v.firstName.$touch()"
                                @blur="$v.firstName.$touch()"
                            ></v-text-field>
                            <v-text-field
                                v-model="lastName"
                                label="Last Name"
                                required
                                :error-messages="lastNameErrors"
                                @input="$v.lastName.$touch()"
                                @blur="$v.lastName.$touch()"
                            ></v-text-field>
                            <v-text-field
                                v-model="email"
                                label="E-mail"
                                required
                                :error-messages="emailErrors"
                                @input="$v.email.$touch()"
                                @blur="$v.email.$touch()"
                            ></v-text-field>
                            <v-text-field
                                v-model="password"
                                :append-icon="showPassword ? 'visibility_off' : 'visibility'"
                                :type="showPassword ? 'text' : 'password'"
                                label="Password"
                                @click:append="showPassword = !showPassword"
                                required
                                :error-messages="passErrors"
                                @input="$v.password.$touch()"
                                @blur="$v.password.$touch()"
                            ></v-text-field>
                            <v-btn color="primary">Sign-Up</v-btn>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-tab-item>
        </v-tabs>
    </v-card-text>
</v-card>
</template>

<script>
import { validationMixin } from 'vuelidate';
import { required, minLength, email } from 'vuelidate/lib/validators';

export default {
  name: 'login-component',

  mixins: [validationMixin],

  validations: {
      firstName: { required, minLength: minLength(4) },
      lastName: { required },
      email: { required, email },
      password: { required, minLength: minLength(8) },
  },

  data() {
    return {
      showPassword: false,
      email: '',
      password: '',
      firstName: '',
      lastName: '',
    };
  },

  computed: {
    firstNameErrors() {
      const errors = [];
      if (!this.$v.firstName.$dirty) return errors;
      !this.$v.firstName.required && errors.push('First Name is required');
      return errors;
    },
    lastNameErrors() {
      const errors = [];
      if (!this.$v.lastName.$dirty) return errors;
      !this.$v.lastName.required && errors.push('Last Name is required');
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push('Must be valid e-mail');
      !this.$v.email.required && errors.push('E-mail is required');
      return errors;
    },
    passErrors() {
      const errors = [];
      if (!this.$v.password.$dirty) return errors;
      !this.$v.password.minLength && errors.push('Password must be at least 8 characters long');
      !this.$v.password.required && errors.push('Password is required');
      return errors;
    },
  },

  methods: {
    signinf() {
      this.$v.$touch();
    },
    signup_f() {
      this.$v.$touch();
    },
  },
};
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
