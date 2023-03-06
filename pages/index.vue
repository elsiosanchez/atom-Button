<template>
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
      <el-auto-resizer>
        <template #default="{ height, width }">
          <el-table-v2
            :columns="columns"
            :data="data"
            :width="width"
            :height="height"
            fixed
          />
        </template>
      </el-auto-resizer>
    </div>
  </el-card>
</template>

<script lang="ts" setup>
  // Name	Description	Default	Control

  const columns = [
    {
      title: 'name',
      dataKey: 'name',
      width: 400
    },
    {
      title: 'Description',
      dataKey: 'description',
      width: 400
    },
    {
      title: 'Default',
      dataKey: 'default',
      width: 400
    },
    {
      title: 'Control',
      dataKey: 'control',
      width: 400
    }
  ]
//   const generateColumns = (length = 10, prefix = 'column-', props?: any) =>
//   Array.from({ length }).map((_, columnIndex) => ({
//     ...props,
//     key: `${prefix}${columnIndex}`,
//     dataKey: `${prefix}${columnIndex}`,
//     title: `Column ${columnIndex}`,
//     width: 150,
//   }))

// const generateData = (
//   columns: ReturnType<typeof generateColumns>,
//   length = 200,
//   prefix = 'row-'
// ) =>
//   Array.from({ length }).map((_, rowIndex) => {
//     return columns.reduce(
//       (rowData, column, columnIndex) => {
//         rowData[column.dataKey] = `Row ${rowIndex} - Col ${columnIndex}`
//         return rowData
//       },
//       {
//         id: `${prefix}${rowIndex}`,
//         parentId: null,
//       }
//     )
//   })

// const columns = [
//   {
//     dataKey: "name",
//     title: "alo",
//     width: 150
//   }
// ]
// const data = [
//   {
//     name: 'content'
//   }
// ]
  console.log({ columns })
  const data = [
    {
      name: 'content',
      description: 'Type here to fill the button (only for testing in Storybook). For development use default slot, described below, to change the content.',
      default: '-',
      control: 'test'
    },
    {
      name: 'Link',
      description: `Link for 'a' tag. string object`,
      default: 'Null',
      control: '-'
    }
  ]
  console.log({ data })
</script>

<style scoped>
  .card-header-attributes{
    text-align: center;
  }
  .title {
    font-size: 20px;
  }
</style>
