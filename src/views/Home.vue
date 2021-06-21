<template>
    <div class="home">
        <el-row>
            <el-col :span="12" :offset="6" class="center">
                <el-button @click="togglePetForm" type="primary">Add New Pet</el-button>
            </el-col>
        </el-row>
         <el-row>
            <el-col :span="12" :offset="6">
                <el-form @submit.native.prevent="handleSubmit" v-if="showForm" :model="form" label-width="120px" class="create-form">
                    <el-form-item label="Name:">
                        <el-input v-model="form.name"></el-input>
                    </el-form-item>
                    <el-form-item label="Species:">
                        <el-select v-model="form.species" placeholder="please select your pet">
                        <el-option label="Cat" value="cat"></el-option>
                        <el-option label="Dog" value="dog"></el-option>
                        </el-select>
                    </el-form-item>
                    <el-form-item label="Age:">
                        <el-input v-model="form.age"></el-input>
                    </el-form-item>
                    <el-form-item>
                        <el-button type="submit" >Create</el-button>
                        <el-button>Cancel</el-button>
                    </el-form-item>
                </el-form>
            </el-col>
            
        </el-row>
        
    </div>
</template>
<script>
import { mapActions, mapGetters } from 'vuex';
export default {
    name: 'Home',
    data() {
      return {
        form: {
          name: '',
          age: 0,
          species: null
        },
        showForm: false
      }
    },
    methods: {
      togglePetForm(){
          this.showForm = !this.showForm
      },
      ...mapActions([
          'addPet'
      ]),
      handleSubmit() {
        const { species, age, name } = this.form
        const payload = {
              species,
              pet: {
                name,
                age
              }
        }
        console.log("ok")
        this.addPet(payload)
        this.form = {
            name: '',
            age: 0,
            species: null
        }

      }
    },
    computed: {
        ...mapGetters([
            'animalsCount',
            'getAllCats'
        ])
    }
}
</script>
<style scoped>
    .create-form{
        margin-top: 35px;
    }
    .center {
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>