<template>
	<div>
		<section id="contactUs" class="page-section secPad">
			<div class="container">
				<div class="row">
					<div class="heading text-center">
						<h2>Let's Keep In Touch!</h2>
						<p>Thank you for visiting out my profile. If you would like to get into contact with me, please fill out the form below.</p>
					</div>
				</div>
				<div class="m-0">
                    <div>
                        <b-alert :show="dismissCountDown" dismissible fade variant="success" @dismiss-count-down="countDownChanged"> Thank you for your feedback! </b-alert>
                    </div>
					<div class="row">
						<div class="col-md-8">							
							<form method="post" @submit.prevent="btnSubmit()" id="contactfrm" role="form">
								<div class="row">
									<div class="col-sm-6">
										<div class="form-group">
											<label for="name">Name</label>
											<input type="text" v-model="txtName" class="form-control" name="name" id="name" placeholder="Enter name" required title="Please enter your name (at least 2 characters)"> </div>
										<div class="form-group">
											<label for="email">Email</label>
											<input type="email" v-model="txtEmail" class="form-control" name="email" id="email" placeholder="Enter email" required title="Please enter a valid email address"> </div>
										<div class="form-group">
											<label for="text">Phone Number</label>
											<input type="text" v-model="txtNumber" class="form-control" name="phnnum" id="phnnum" placeholder="Enter phone number" @input="handleInput" required title="Please enter phone number">
											<p v-if="showErrorMessage" class="text-danger">Please enter a valid 10-digit number.</p>
										</div>
									</div>
									<div class="col-sm-6">
										<div class="form-group">
											<label for="comments">Comments</label>
											<textarea name="comment" v-model="txtComments" class="form-control" id="comments" cols="3" rows="5" placeholder="Enter your message…" required title="Please enter your message (at least 10 characters)"></textarea>
										</div>
										<button name="submit" :disabled="isBtnClick" type="submit" class="btn btn-lg btn-primary" id="submit">Submit</button>
										<div class="result"></div>
									</div>
								</div>
							</form>
						</div>
						<div class="col-md-4">
							<h4>Address:</h4> 
                            <address>
                                32-28-4/3,<br>
                                Atchayammapeta,<br>
                                Allipuram,<br>
                                Visakhapatnam, 530004.
                                <br>
                            </address>
							<h4>Phone:</h4> 
                            <address>
                                +91 7989586850<br>
                            </address> 
                        </div>
					</div>
				</div>
			</div>
		</section>
		<footer>
			<div class="container">
				<div class="social text-center">
					<a href="#">
						<font-awesome-icon :icon="['fab', 'twitter']" /> 
                    </a>
					<a href="#">
						<font-awesome-icon :icon="['fab', 'facebook-f']" /> 
                    </a>
					<a href="#">
						<font-awesome-icon :icon="['fas', 'basketball']" /> 
                    </a>
					<a href="#">
						<font-awesome-icon :icon="['fab', 'flickr']" /> 
                    </a>
					<a href="#">
						<font-awesome-icon :icon="['fab', 'github']" /> 
                    </a>
				</div>
				<div class="clear"></div>
			</div>
		</footer>
	</div>
</template>
<script>
import Email from '../assets/script/common.js';
export default {
    name: 'FooterView',
    data() {
        return {
            inputValue: '',
            showErrorMessage: false,
            txtName: "",
            txtEmail: "",
            txtNumber: "",
            txtComments: "",
            dismissSecs: 5,
            dismissCountDown: 0,
            showDismissibleAlert: false,
            isBtnClick: false,
        }
    },
    methods: {
        handleInput(event) {
            const input = event.target.value;
            const numbersOnly = input.replace(/\D/g, '');
            const trimmedValue = numbersOnly.slice(0, 10);
            this.inputValue = trimmedValue;
            this.showErrorMessage = input !== trimmedValue || trimmedValue.length !== 10;
        },
        async btnSubmit() {
            this.isBtnClick = true;
            if (!this.showErrorMessage) {
                let resp = await Email.send({
                    Host: "smtp.elasticemail.com",
                    Username: "mendavenkatasuresh@gmail.com",
                    Password: "E10542A497C7B9339B24AE38A3D0896255F2",
                    // SecureToken:"84E67612B44156E29B5272C6E5B125C3C0F6818E598D811180A9092607CC3448320D089F86A01BE4DCBE6737773B5F4B",
                    To: 'mendavenkatasuresh@gmail.com',
                    From: "noworknofood7989@gmail.com",
                    Subject: "Feed back from Personal Website.",
                    Body: "Name : <strong>" + this.txtName + "</strong><br>Email : <strong>" + this.txtEmail + "</strong><br>Phone Number : <strong>" + this.txtNumber + "</strong><br>Comments : <strong>" + this.txtComments + "</strong>"
                });
                console.log(resp);
                if (resp == "OK") {
                    this.isBtnClick = false;
                    this.showAlert();
                    this.txtName = "";
                    this.txtEmail = "";
                    this.txtNumber = "";
                    this.txtComments = "";
                }
                else
                    this.isBtnClick = false;
            }
        },
        countDownChanged(dismissCountDown) {
            this.dismissCountDown = dismissCountDown
        },
        showAlert() {
            this.dismissCountDown = this.dismissSecs
        }
    }
}
</script>