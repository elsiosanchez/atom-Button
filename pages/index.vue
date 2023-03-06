<template>
  <el-card class="box-card">
    <el-card class="box-card">
      <template #header>
        <div class="card-header-attributes">
          <p class="title">
            <b>
              <i>
                {{ "Example" }}
              </i>
            </b>
          </p>
        </div>
      </template>
      <div style="height: 50px; text-align: center">
        <el-button :type="typeButton" :disabled="isDisable">
          {{ input }}
        </el-button>
      </div>
    </el-card>
    <el-card class="box-card">
      <template #header>
        <div class="card-header-attributes">
          <p class="title">
            <b>
              <i>
                {{ "Atributos" }}
              </i>
            </b>
          </p>
        </div>
      </template>
      <div style="height: 400px">
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="name" label="Name" width="120" />
          <el-table-column prop="description" label="Description" />
          <el-table-column prop="default" label="Default" width="200" />
          <el-table-column label="Control">
            <template #default="scope">
              <el-input v-if="scope.row.type === 'input'" v-model="input" />
              <el-select
                v-else-if="scope.row.type === 'select'"
                v-model="typeButton"
                style="width: 100%"
              >
                <el-option
                  v-for="item in options"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value"
                />
              </el-select>
              <el-switch
                v-else-if="scope.row.type === 'optionsBoolean'"
                v-model="isDisable"
                class="mb-2"
                style="
                  --el-switch-on-color: #13ce66;
                  --el-switch-off-color: #ff4949;
                "
                active-text="true"
                inactive-text="false"
              />
              <!-- <el-select
                v-else-if="scope.row.type === 'optionsBoolean'"
                v-model="isDisable"
                style="width: 100%"
              >
                <el-option
                  v-for="(item, index) in optionsBoolean"
                  :key="index"
                  :label="item.label"
                  :value="item.value"
                />
              </el-select> -->
              <span v-else> {{ scope.row.control }} </span>
            </template>
          </el-table-column>
        </el-table>
      </div>
    </el-card>
  </el-card>
</template>

<script lang="ts" setup>
import { ref } from "vue";
const input = ref("Example");
const typeButton = ref("Default");
const isDisable = ref(false);
const options = [
  {
    value: "",
    label: "Default",
  },
  {
    value: "primary",
    label: "Primary",
  },
  {
    value: "success",
    label: "Success",
  },
  {
    value: "info",
    label: "Info",
  },
  {
    value: "warning",
    label: "Warning",
  },
  {
    value: "danger",
    label: "Danger",
  },
];

const tableData = [
  {
    name: "content",
    description:
      "Type here to fill the button (only for testing in Storybook). For development use default slot, described below, to change the content.",
    default: "-",
    control: input.value,
    type: "input",
  },
  {
    name: "type",
    description: "Type the Button.",
    default: "Default",
    control: "-",
    type: "select",
  },
  {
    name: "Disabled",
    description:
      "The disabled attribute determines if a button is disabled. Use the disabled attribute to determine if a button is disabled. Accepts a Boolean value.",
    default: "False",
    control: "-",
    type: "optionsBoolean",
  },
];
</script>

<style scoped>
.card-header-attributes {
  text-align: center;
}
.title {
  font-size: 20px;
}
</style>
