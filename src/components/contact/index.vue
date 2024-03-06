<template>
    <form>
        <div class="row">
            <div class="col-xl-12">
                <h1>Contact Person</h1>
                <hr>

                <div class="form-group">
                    <label for="name">Nama</label>
                    <input 
                    type="text" 
                    id="name" 
                    class="form-control"
                    v-model.lazy="formData.name" />
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input 
                    type="email" 
                    id="email" 
                    class="form-control"
                    v-model="formData.email" />
                </div>
                <div class="form-group">
                    <label for="subject">Subject</label>
                    <input 
                    type="text" 
                    id="subject" 
                    class="form-control"
                    v-model="formData.subject" />
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea
                    id="message" 
                    rows="3"
                    class="form-control"
                    v-model="formData.message" >
                    </textarea>
                </div>
                <div class="form-group">
                    <h5>Want to get Promotion ?</h5>
                    <div class="form-check">
                        <input
                        class="form-check-input"
                        type="checkbox"
                        value="Newsletter"
                        id="newsletter"
                        v-model="formData.extras">
                        <label class="form-check-label" for="newsletter">Newsletter</label>
                    </div>
                    <div class="form-check">
                        <input
                        class="form-check-input"
                        type="checkbox"
                        value="Promotions"
                        id="promotions"
                        v-model="formData.extras">
                        <label class="form-check-label" for="promotions">Promotions</label>
                    </div>

                </div>

                <div class="form-group">
                    <h5>Who Are You ?</h5>
                    <div class="form-check">
                        <input
                        class="form-check-input"
                        type="radio"
                        value="male"
                        id="male"
                        v-model="formData.gender">
                        <label class="form-check-label" for="male">Male</label>
                    </div>
                    <div class="form-check">
                        <input
                        class="form-check-input"
                        type="radio"
                        value="female"
                        id="female"
                        v-model="formData.gender">
                        <label class="form-check-label" for="female">Promotions</label>
                    </div>

                </div>
                <div class="form-group">
                    <label for="country">Country</label>
                <select v-model="formData.country" class="form-control" id="country">
                    <option v-for="(country, index) in listCountry" :key="index" >
                    {{ country }}
                    </option>
                </select>

                </div>
                <hr>
                <button class="btn btn-primary" 
                @click.prevent="submitForm">
                    Submit
                </button> |
                <button class="btn btn-primary" 
                @click.prevent="getData">Get Data</button>
            </div>
        </div>
    </form>
</template>
<script>
export default{
    data(){
        return {
            formData:{
            name:'',
            email:'',
            subject:'',
            message:'',
            extras:[],
            gender:'',
            country:'',
            },
            listCountry:[
                'Indonesia',
                'Malaysia',
                'Thailand',
                'Vietnam',
                'Singapore'
            ]
        }
    },
    methods:{
        submitForm(){
            console.log(this.formData)
        },
        getData(){
            this.formData.name='Boy Novriyal'
            this.formData.email='boynovrial@gmail.com'
            this.formData.subject='Self Motivation'
            this.formData.message='Hello World!! \ndont give up!! \nkeep strong and believe yourself'
            this.formData.gender='male'
        }
    }
}
</script>