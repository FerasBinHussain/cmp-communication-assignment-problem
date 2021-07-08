<template>
    <section>
        <div>
            <active-user
             v-for="user in users"
            :key="user.name"
            :name="user.name"
            :age="user.age"
            > </active-user>
        </div>
        <div>
            <user-data
            @add-user="addUser"
            > </user-data>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            users: [
                {
                    name: 'knjb',
                    age: '4',
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