<template>
    <Form @submit="onSubmit">
        <hr>
        <label for="name">Name</label>
        <Field 
        class="form-control"
        name="name" 
        :rules="validateName" 
        placeholder="Input Your name here !"/>
        <ErrorMessage name="name" as="div" v-slot="{message}">
            <div class="alert alert-danger" role="alert">
                {{ message }}
            </div>
         </ErrorMessage>

         <label for="Email">Email</label>
        <Field 
        name="email" 
        :rules="validateEmail" 
        v-slot="{ field, errors, errorMessage }">
         <input
         type="text"
         id="email"
         class="form-control"
         placeholder="Input Your Email here !" 
         v-bind="field"
         :class="{'is-invalid':errors.length !==0}"
         >
         <div
         class="alert alert-danger"
         role="alert"
         v-if="errors.length !==0">
        {{ errorMessage }}
        </div>
        </Field>
         <!-- <ErrorMessage name="email" as="div" v-slot="{message}">
            <div class="alert alert-danger" role="alert">
                {{ message }}
            </div>
         </ErrorMessage> -->
        <div class="form-group">
            <label for="message">Message</label>
            <Field name="message"
            :rules="validateMessage"
            v-slot="{ field, errors , errorMessage }">
            <textarea
            id="message"
            rows="3"
            class="form-control"
            placeholder="Input Your Message here !"
            v-bind="field"
            :class="{'is-invalid':errors.length !==0}"
            >
            </textarea>
            <div
            class="alert alert-danger"
            role="alert"
            v-if="errors.length !==0"
            >
                {{ errorMessage }}
            </div>
        
        </Field> 

        </div>
        <hr>
       

        <button class="btn btn-primary">Submit</button>
    </Form>
</template>
<script>
import {Field, Form, ErrorMessage} from "vee-validate"

export default{
    components:{
        Field,Form,ErrorMessage
    },
    methods:{
        isRequired(value){
            if(!value){
                return 'name is required'
            }
            return true
        },
        validateName(value){
            if(!value){
                return 'name is required'
            }
            return true
        },
        validateEmail(value){
            if(!value){
                return 'email is required';
            }
            if(!/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/i.test(value)){
                return 'Bad Email'
            }
            return true;       
        },
        validateMessage(value){
            if(!value){
                return 'Email is required'
            }
            return true
        },
        onSubmit(values,{ resetForm }){
            console.log(values);
            resetForm();
        }
    }
}
</script>