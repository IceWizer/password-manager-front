<template>
    <div>
        <h1>Logout</h1>
    </div>
</template>

<script>
import { logout } from "@/auth/utils/connection";

export default {
    name: "Log-out",
    setup() {
        return {

        }
    },
    created() {
        this.logout();
    },
    methods: {
        logout() {
            this.$store.dispatch('authStore/logout')
                .then((response) => {
                    logout();
                    this.$router.push({ name: 'login' });
                })
                .catch((error) => {
                    console.log(error);
                });
        }
    }
}
</script>