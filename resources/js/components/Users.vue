<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-header">Users Component</div>

                    <div class="card-body">
                        <div class="form-group row">
                            <div class="col-md-12">
                                <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#addNew">Create</button>
                            </div>
                        </div>

                        <div class="form-group row">
                            <div class="col-md-12">
                                <table class="table table-striped">
                                    <thead>
                                        <tr>
                                            <th>ID</th>
                                            <th>Username</th>
                                            <th>First name</th>
                                            <th>Last name</th>
                                            <th>Address</th>
                                            <th>Postcode</th>
                                            <th>Contact no</th>
                                            <th>Email address</th>
                                            <th>Action</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr>
                                            <td>1</td>
                                            <td>Mark</td>
                                            <td>Otto</td>
                                            <td>@mdo</td>
                                            <td>1</td>
                                            <td>Mark</td>
                                            <td>Otto</td>
                                            <td>@mdo</td>
                                            <td>
                                                <a href="#" class="btn btn-success">Edit</a> 
                                                <a href="#" class="btn btn-danger">Delete</a>
                                            </td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>


        <!-- Modal -->
        <div class="modal fade" id="addNew" tabindex="-1" role="dialog" aria-labelledby="addNewLabel" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered" role="document">
                <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="addNewLabel">Add New User</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                    </button>
                </div>

                <form @submit.prevent="createUser">
                <div class="modal-body">
                    <!-- Firstname -->
                    <div class="form-group">
                        <input v-model="form.firstname" type="text" name="firstname"
                            placeholder="First name"
                            class="form-control" :class="{ 'is-invalid': form.errors.has('firstname') }">
                        <has-error :form="form" field="firstname"></has-error>
                    </div>

                    <!-- Lastname -->
                    <div class="form-group">
                        <input v-model="form.lastname" type="text" name="lastname"
                            placeholder="Last name"
                            class="form-control" :class="{ 'is-invalid': form.errors.has('lastname') }">
                        <has-error :form="form" field="lastname"></has-error>
                    </div>

                    <!-- Email address -->
                    <div class="form-group">
                        <input v-model="form.email" type="email" name="email"
                            placeholder="Email address"
                            class="form-control" :class="{ 'is-invalid': form.errors.has('email') }">
                        <has-error :form="form" field="email"></has-error>
                    </div>

                    <!-- Password -->
                    <div class="form-group">
                        <input v-model="form.password" type="password" name="password" id="password"
                            placeholder="Password"
                            class="form-control" :class="{ 'is-invalid': form.errors.has('password') }">
                        <has-error :form="form" field="password"></has-error>
                    </div>

                    <!-- Type -->
                    <div class="form-group">
                        <select name="type" v-model="form.type" id="type" 
                        class="form-control" :class="{ 'is-invalid': form.errors.has('type') }">
                            <option value="">Select user type</option>
                            <option value="admin">Admin</option>
                            <option value="user">Standard User</option>
                        </select>
                        <has-error :form="form" field="type"></has-error>
                    </div>

                    <!-- Address -->
                    <div class="form-group">
                        <textarea v-model="form.address" name="address" id="address" rows="3"
                        placeholder="Address"
                        class="form-control" :class="{ 'is-invalid': form.errors.has('address') }"></textarea>
                        <has-error :form="form" field="address"></has-error>
                    </div>

                    <!-- Postcode -->
                    <div class="form-group">
                        <input v-model="form.postcode" type="text" name="postcode" id="postcode"
                            placeholder="Post code"
                            class="form-control" :class="{ 'is-invalid': form.errors.has('postcode') }">
                        <has-error :form="form" field="postcode"></has-error>
                    </div>  

                    <!-- Contact no -->
                    <div class="form-group">
                        <input v-model="form.contactno" type="text" name="contactno" id="contactno"
                            placeholder="Contact no"
                            class="form-control" :class="{ 'is-invalid': form.errors.has('contactno') }">
                        <has-error :form="form" field="contactno"></has-error>
                    </div>                                                           
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
                    <button type="submit" class="btn btn-primary">Save changes</button>
                </div>

                </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                form: new Form({
                    firstname: '',
                    lastname: '',
                    email: '',
                    password: '',
                    type: '',
                    address: '',
                    postcode: '',
                    contactno: ''
                })
            }
        },
        methods: {
            createUser() {
                this.form.post('api/user');
            }
            
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
