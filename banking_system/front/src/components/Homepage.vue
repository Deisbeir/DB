<template>
  <v-container>
    <v-row>
      <v-col cols="8" offset="2" align="space-around">
        <h1 justify="center" class="py-12 display-5">分行相关信息</h1>

        <v-card outlined class="my-4 px-4" v-for="(dType, idxType) in dataType" :key="idxType">
          <v-card-title>{{ dataType[idxType] }}</v-card-title>
          <v-simple-table>
            <template v-slot:default>
              <thead>
                <tr>
                  <th
                    class="text-middle"
                    v-for="(dLabel, idxLabel) in label[idxType]"
                    :key="idxLabel"
                  >{{ dLabel }}</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(dOut, idxOut) in data[idxType]" :key="idxOut">
                  <td v-for="(dIn, idxIn) in dOut" :key="idxIn">{{ dIn }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Welcome",

  data: () => ({
    dataType: ["网点分布", "职员介绍", "部门介绍", "部门经理介绍"],
    label: [
      ["分行名", "城市"],
      [
        "员工 ID",
        "姓名",
        "联系方式",
        "家庭住址",
        "开始工作日期",
        "部门 ID"
      ],
      [
        "部门 ID",
        "部门名",
        "类型",
        "部门经理",
        "所属分行"
      ],
      ["员工 ID", "部门 ID"]
    ],
    data: [
      [
        ["北京分行", "北京"],
        ["上海分行", "上海"],
        ["合肥分行", "合肥"],
        ["乌鲁木齐分行", "乌鲁木齐"],
        ["伊犁分行", "伊犁"]
      ],
      [
        ["staff_1",
        "staffA",
        "18512312345",
        "合肥市蜀山区",
        "2012-01-11",
        "depart_1"],
        ["staff_2",
        "staffB",
        "18732332333",
        "合肥市包河区",
        "2014-01-10",
        "depart_1"],
        ["staff_3",
        "staffC",
        "13323311451",
        "北京市昌平区",
        "2016-06-01",
        "depart_2"],
        ["staff_4",
        "staffD",
        "17344455555",
        "北京市海淀区",
        "2016-11-24",
        "depart_4"],
        ["staff_5",
        "staffE",
        "18912345678",
        "北京市朝阳区",
        "2018-02-02",
        "depart_5"],
        ["staff_6",
        "staffF",
        "13012345678",
        "上海市浦东区",
        "2020-07-04",
        "depart_3"],
        ["staff_7",
        "staffG",
        "18900011100",
        "乌鲁木齐市天山区",
        "2021-2-24",
        "depart_5"],
        ["staff_8",
        "staffH",
        "18912321232",
        "伊宁市伊宁县",
        "2021-06-03",
        "depart_6"]
      ],
      [
        ["depart_1", "市场部", "普通", "staff_1", "Hefei Bank"],
        ["depart_2", "市场部", "普通", "staff_3", "Beijing Bank"],
        ["depart_3", "市场部", "特殊", "staff_6", "Shanghai Bank"],
        ["depart_4", "人事部", "普通", "staff_4", "Beijing Bank"],
        ["depart_5", "人事部", "普通", "staff_7", "Urumqi Bank"],
        ["depart_6", "人事部", "特殊", "staff_8", "Yili Bank"]
      ],
      [
        ["staff_1", "depart_1"],
        ["staff_3", "depart_2"],
        ["staff_6", "depart_3"],
        ["staff_4", "depart_4"],
        ["staff_7", "depart_5"],
        ["staff_8", "depart_6"] 
      ]
    ]
  })
};
</script>
