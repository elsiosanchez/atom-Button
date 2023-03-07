<template>
  <el-row>
    <el-col :span="24">
      <el-card :body-style="{ padding: '0px' }" style="text-align: center;">
        <div style="padding: 14px">
          <p class="title">
            <b>
              <i>
                {{ "Botón" }}
              </i>
            </b>
          </p>
          <div class="bottom">
            <p>
              El componente del botón base. Este componente funcional de Vue3, Nuxt3 y
              Element-Plus.
            </p>
          </div>
        </div>
      </el-card>
    </el-col>
  </el-row>
  <NuxtPage />
</template>
<style scoped>
  .affix-container {
    text-align: center;
    height: 200px;
    border-radius: 4px;
  }
  .title {
    font-size: 24px;
  }
</style>
