<template>
    <section>
        <div class="float-container">
            <div class="active-users">
                <active-user
                v-for="user in users"
                :key="user.name"
                :name="user.name"
                :age="user.age"
                > </active-user>
            </div>
            <div class="users-data">
                <user-data
                @add-user="addUser"
                > </user-data>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            users: [
                {
                    name: '',
                    age: '',
                }
            ]
        };
    },
    methods: {
        addUser(name, age) {
            const newUser = {
                name: name,
                age: age
            };
            this.users.push(newUser);
        },
    }
}
</script>

<style>
.float-container {
  width: 80%;
  height: 200px;
  margin: auto;
  padding: 10px;

}

.active-users {
  width: 15%;
  height: 200px;
  float: left;
}

.users-data {
  margin-left: 20%;
  height: 200px;
  margin-top: 25px;
}

</style>