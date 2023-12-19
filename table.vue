<template>
  <div class='class-table'>
    <div class='table-wrapper'>
      <div class='tabel-container'>
        <table>
          <thead>
            <tr>
              <th class="null"></th>
              <th v-for='(title, index) in titles' :key='index' :class="{ cretateTime:index == 0 }"> {{ title }}</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for='(item, index) in simulatedData' :key='index' :class="'tr-color-' + index % 2">
              <td class="null"></td>
              <td>{{item.createdate}}</td>
              <td>{{item.name[1]}}**</td>
              <td>{{item.type}}</td>
              <td>{{item.principal}}</td>
              <td>{{item.state == 1?'已处理':'未处理'}}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      titles: ['创建时间', '姓名', '类型', '负责人', '状态'],
      simulatedData: [
        {
          createdate: '2021-11-10 08:32:23',
          name: '陈奇偶',
          type: '健康变化',
          principal: '薛舒淇',
          state: 0
        },
        {
          createdate: '2021-11-10 08:32:23',
          name: '阳欧式',
          type: '健康变化',
          principal: '记语文',
          state: 1
        },
        {
          createdate: '2021-11-10 08:32:23',
          name: '巴特斯',
          type: '健康变化',
          principal: '结搜到',
          state: 0
        },
        {
          createdate: '2021-11-10 08:32:23',
          name: '陈刀片',
          type: '健康变化',
          principal: '曾破山',
          state: 0
        }
      ]
    }
  },
  created () {
  },
  methods: {
  }
}
</script>

<style lang='less' scoped>
@color3:rgba(17, 98, 107, 0.3);
@color5:rgba(17, 98, 107, 0.7);
@bordercolor:rgb(36, 152, 165);
.class-table {
  .table-wrapper {
    width: 100%;
    height: 100%;
    overflow: auto;
  }
  .tabel-container {
    margin: 7px;
    width: 90%;
    margin: auto;
    margin-top: 30px;
    border: 1px solid @bordercolor;
    table {
      // table-layout: fixed;
      width: 100%;
      // 去除表格的默认边框
      border-spacing: 0px;
      border-collapse: collapse;
      thead {
        background-color: @color5;
        th {
          color: #fff;
          line-height: 17px;
          font-weight: normal;
          height: 65px;
          padding: 12px 2px;
          font-size: 30px;
          text-align: center;
        }
        .cretateTime {
          width: 150px;
        }
      }

      tbody {
        // 不同行不同背景色
        .tr-color-0 {
          background: rgba(255, 255, 255, 0);
        }
        .tr-color-1 {
          background: @color3;
        }
        td {
          color: #ffffff;
          line-height: 55px;
          width: 60px;
          padding: 12px 2px;
          font-size: 27px;
          text-align: center;
        }
      }
      .null {
        width: 20px;
      }
    }
  }
}
</style>

