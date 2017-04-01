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
                    <button @click="test" type="submit" class="btn btn-success pull-right">Login</button>
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
            test () {
                //this.$http.headers.common['X-Requested-With'] = 'XMLHttpRequest';
                this.$http.get("http://127.0.0.1:8000/api/test")
                        .then(function(response) {
                            console.log(response);
                        })
            }
        }
    }

</script>

<style></style>