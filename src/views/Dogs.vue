<template>
    <div>
        <el-table
            :data="dogs"
            border
            style="width: 100%">

            <el-table-column
                label="Name"
                width="180"
                cell-click="`/pets/dogs/`">
                <template v-slot:default="table">
                    <router-link :to="`/pets/dogs/${table.row.id }`" tag="span">
                        <el-button type="text" size="mini" prop="name">
                            {{table.row.name }}
                        </el-button>
                    </router-link>
                </template>
            </el-table-column>
            <el-table-column
                prop="breed"
                label="Breed"
                width="180">
            </el-table-column>
            <el-table-column
                prop="gender"
                label="Gender"
                width="180">
            </el-table-column>
            <el-table-column
                prop="color"
                label="Color"
                width="180">
            </el-table-column>
            <el-table-column
                prop="weight"
                label="Weight"
                width="180">
            </el-table-column>
            <el-table-column
                prop="location"
                label="Location">
        </el-table-column>
  </el-table>
    </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
    data() {
      return {
       
      }
    },
    computed: {
        ...mapState([
            'dogs'
        ])
    }
}
</script>