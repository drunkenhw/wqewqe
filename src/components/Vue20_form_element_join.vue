<template>
  <h1>form element join</h1>
  <form action="Vue20_memberList.vue" ref="frm">
    <fieldset>
      <legend>회원가입</legend>
      <div>
        <label for="id" class="title">Id</label>
        <input type="id" ref="id" id="id" />
      </div>
      <div>
        <label for="name" class="title">name</label>
        <input type="text" ref="name" id="name" />
      </div>
      <div>
        <label for="pass" class="title">password</label>
        <input type="password" ref="pass" id="pass" />
      </div>
      <div>
        <label for="repass" class="title">Re-password</label>
        <input type="password" ref="repass" id="repass" />
      </div>
      <div>
        <label class="title">Hobby</label>
        <label :for="item" v-for="(item, i) in hobbyList" :key="i"
          >{{ item }}
          <input
            type="checkbox"
            name="hobby"
            :id="item"
            :value="item"
            v-model="hobby"
          />
        </label>
      </div>
      <div>
        <label class="title">gender</label>
        <label :for="item" v-for="(item, i) in genderList" :key="i"
          >{{ item }}
          <input
            type="radio"
            name="gender"
            :id="item"
            :value="item"
            v-model="gender"
            :ref="item"
          />
        </label>
      </div>
      <div>
        <label for="mobile" class="title">Mobile</label>
        <select v-model="mobile" id="mobile">
          <option :value="item" v-for="item in mobileList" :key="item">
            {{ item }}
          </option>
        </select>
        <input type="text" name="mobile1" id="mobile1" class="m1" ref="mobile1" />-
        <input type="text" name="mobile2" id="mobile2" class="m1" ref="mobile2" />
        <input type="hidden" name="mobile" ref="mobile" />
      </div>
      <div>
        <label for="id" class="title"></label>
        <button ref="btnJoin" @click.prevent="join" class="btn-margin">
          가입
        </button>
        <button @click.prevent="cancel">취소</button>
      </div>
    </fieldset>
  </form>
</template>

<script>
export default {
  data() {
    return {
      hobby: [],
      hobbyList: ["sc", "bg", "bk"],
      gender: "여",
      genderList: ["남", "여"],
      mobile: "010",
      mobileList: ["010", "011", "016"],
    };
  },
  methods: {
    cancel() {
    const frm = this.$refs.frm
   
    frm.reset()
    document.querySelector("#여").checked=true
    
      
    },
    join() {
        // e.preventDefault();
      const frm = this.$refs.frm;
      const id = this.$refs.id;
      const name = this.$refs.name;
      const pass = this.$refs.pass;
      const repass = this.$refs.repass;
    //   const mobile = this.$refs.mobile;
      const mobile1 = this.$refs.mobile1;
      const mobile2 = this.$refs.mobile2;
      if (id.value == "") {
        alert("id입력");
        id.focus();
      }
      else if (name.value == "") {
        alert("name입력");
        name.focus();
      }
      else if (pass.value == "") {
        alert("password입력");
        pass.focus();
      }
      else if (pass.value != repass.value) {
        alert("password확인");
        pass.focus();
      }
    //   else if (mobile.value == "") {
    //     alert("전화번호 입력");
    //     mobile1.focus();
    //   }
      else if (mobile1.value == "") {
        alert("전화번호 입력");
        mobile1.focus();
      }
      else if (mobile2.value == "") {
        alert("전화번호 입력");
        mobile2.focus();
      }else{

            frm.submit()
      }
    },
  },
};
</script>

<style>
.title {
  width: 120px;
  margin: 5px;
  text-align: left;
  display: inline-block;
}
fieldset div {
  text-align: left;
}
.m1 {
  width: 50px;
}
.btn-margin {
  margin-right: 30px;
}
</style>
