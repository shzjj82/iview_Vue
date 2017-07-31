<template>
  <div id="app">
    <div class="layout" >
          <Row type='flex'>
              <i-col class="layout-menu-left" span='5'>
                  <Menu active-name="1-2" theme="dark" width="auto" :open-names="['1']">
                    <div class="layout-logo-left"></div>
                    <Submenu name="1">
                        <template slot="title">
                            <Icon type="ios-navigate"></Icon>
                            Greate Mix
                        </template>
                        <Menu-item name="1-1">Step 1</Menu-item>
                        <Menu-item name="1-2">Step 2</Menu-item>
                        <Menu-item name="1-3">Step 3</Menu-item>
                        <Menu-item name="1-4">Step 4</Menu-item>
                    </Submenu>
                    <Submenu name="2">
                        <template slot="title">
                            <Icon type="ios-keypad"></Icon>
                            MixList
                        </template>
                    </Submenu>
                    <Submenu name="3">
                        <template slot="title">
                            <Icon type="ios-analytics"></Icon>
                             Greate Category
                        </template>
                    </Submenu>
                </Menu>
              </i-col>
               <i-col span="19">
                <div class="layout-header"></div>
                <div class="layout-breadcrumb">
                    <Breadcrumb>
                        <Breadcrumb-item href="#">MixMatch</Breadcrumb-item>
                        <Breadcrumb-item>Greate Mix</Breadcrumb-item>
                    </Breadcrumb>
                </div>
                <div class="layout-content">
                    <div class="layout-content-main">
                      <template>
                          <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" :label-width="80">
                              <Form-item label="Name" prop="name">
                                  <Input v-model="formValidate.name" placeholder="请输入姓名"></Input>
                              </Form-item>
                              <Form-item label="Enname" prop="Enname">
                                  <Input v-model="formValidate.mail" placeholder="请输入邮箱"></Input>
                              </Form-item>
                              <Form-item label="Pic" prop="Pic">
                                  <Input v-model="formValidate.name" placeholder="请输入姓名">
                                    <Button slot="append" icon="ios-search" :loading="loading" @click="toLoading">
                                          <span v-if="!loading"></span>
                                          <span v-else></span>
                                    </Button>
                                  </Input>
                              </Form-item>
                              <Form-item label="Content" prop="Content">
                                  <Input v-model="formValidate.mail" placeholder="请输入邮箱" type='textarea'></Input>
                              </Form-item>
                          </Form>
                      </template>
                    </div>
                </div>
                <div class="layout-copy">
                    2011-2016 &copy; TalkingData
                </div>
            </i-col>
          </Row>
    </div>
  </div>
</template>

<script>
export default {
  data (){
    return {
      formValidate:{
        input1:'',
        input2:'',
        input3:''
      },
      loading: false,
      ruleValidate: {
          name: [
                 { required: true, message: 'name不能为空', trigger: 'blur' }
          ],
          Enname: [
                 { required: true, message: 'Enname不能为空', trigger: 'blur' }
          ],
          Pic: [
                 { required: true, message: 'Pic不能为空', trigger: 'blur' }
          ],
          Content: [
                 { required: true, message: 'Content不能为空', trigger: 'blur' }
                ],
          interest: [
                 { required: true, type: 'array', min: 1, message: '至少选择一个爱好', trigger: 'change' },
                 { type: 'array', max: 2, message: '最多选择两个爱好', trigger: 'change' }
          ],
          date: [
                 { required: true, type: 'date', message: '请选择日期', trigger: 'change' }
                ],
          time: [
                 { required: true, type: 'date', message: '请选择时间', trigger: 'change' }
          ],
          desc: [
                  { required: true, message: '请输入个人介绍', trigger: 'blur' },
                  { type: 'string', min: 20, message: '介绍不能少于20字', trigger: 'blur' }
          ]}
    }
  },
  methods:{
    a(){
      alert(1)
    },
    toLoading () {
      this.loading = true;
    },
  }

}
</script>

<style scoped>
    .layout{
        border: 1px solid #d7dde4;
        background: #f5f7f9;
        position: relative;
    }
    .layout-breadcrumb{
        padding: 10px 15px 0;
    }
    .layout-content{
        min-height: 1000px;
        margin: 15px;
        overflow: hidden;
        background: #fff;
        border-radius: 4px;
    }
    .layout-content-main{
        padding: 10px;
    }
    .layout-copy{
        text-align: center;
        padding: 10px 0 20px;
        color: #9ea7b4;
    }
    .layout-menu-left{
        background: #464c5b;
    }
    .layout-header{
        height: 60px;
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }
    .layout-logo-left{
        width: 90%;
        height: 30px;
        background: #5b6270;
        border-radius: 3px;
        margin: 15px auto;
    }
</style>
