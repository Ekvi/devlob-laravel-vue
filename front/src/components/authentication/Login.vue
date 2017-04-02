<template>
    <div class="row">
        <div class="col-md-6 col-md-offset-3">
            <div class="panel panel-default">
                <div class="panel-body">
                    <div class="form-group">
                        <input type="email" class="form-control" v-model="email" placeholder="Email">
                    </div>
                    <div class="form-group">
                        <input type="password" class="form-control" v-model="password" placeholder="Password">
                    </div>
                    <button @click="login" type="submit" class="btn btn-success pull-right">Login</button>
                </div>
            </div>
        </div>
        <pre>
            {{ $data }}
        </pre>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                email: '',
                password: ''
            }
        },
        methods: {
            login () {
                var data = {
                    client_id: 2,
                    client_secret: 'nOTegApIEuA7nvsDEkdq4OR5J07MAq9JzcS0Q6wj',
                    grant_type: 'password',
                    username: this.email,
                    password: this.password,
                };

                this.$http.post("http://127.0.0.1:8000/oauth/token", data)
                //this.$http.get("http://127.0.0.1:8000/api/test")
                        .then(response => {
                            console.log(response);
                        });
                        /*.then(function(response) {
                            console.log(response);
                        })*/
            }
        }
    }

</script>

<style></style>