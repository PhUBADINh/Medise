<template>
    <div class="bg-gray-100 h-screen flex items-center justify-center bg-[url('./img/backgroundlogIn.jpg')] bg-cover">
      <div class="absolute inset-0 bg-black opacity-30"></div>
      <div class="bg-white shadow-lg z-20 rounded-l-[30px] min-h-[30rem] border-black rounded-2xl flex w-full max-w-4xl">
        <!-- Right side (Description) -->
        <div class="w-1/2 p-8 bg-[#10DBAC] text-white flex items-start border-[2px] border-black justify-center rounded-2xl">
          <div class="text-center flex flex-col justify-center mt-[-2.5rem]">
            <div class="flex justify-center flex-col">
              <h2 class="text-[2.7rem] w-[16rem] mt-[5rem] font-bold text-black">มีบัญชีแล้ว</h2>
              <h1 class="text-[2rem] w-full ml-1 font-bold mb-2 text-black">ใช่หรือไม่ ?</h1>
            </div>
            <div>
              <p class="text-[1.5rem] text-black">เข้าสู่ระบบเลยตอนนี้</p>
            </div>
  
            <div class="mt-4">
              <RouterLink :to="{ name: 'login' }">
                <button class="bg-white h-[3.3rem] w-[17dvw] text-black text-[1.5rem] rounded-[50rem] hover:bg-[#656565] transition-all duration-300">
                  เข้าสู่ระบบ
                </button>
              </RouterLink>
            </div>
          </div>
        </div>
  
        <!-- Left side (Sign Up) -->
        <div class="w-1/2 p-8 flex flex-col items-center mt-[-1rem]">
          <h1 class="text-[1.8rem] font-bold mb-4">สมัครสมาชิก</h1>
          <form @submit.prevent="handleSignUp" class="space-y-[12px]">
            <label class="input input-bordered flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
                <path d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6ZM12.735 14c.618 0 1.093-.561.872-1.139a6.002 6.002 0 0 0-11.215 0c-.22.578.254 1.139.872 1.139h9.47Z" />
              </svg>
              <input type="text" id="name" v-model="username" class="grow" placeholder="Username" />
            </label>
            <div>
              <label class="input input-bordered flex items-center gap-2">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
                  <path d="M2.5 3A1.5 1.5 0 0 0 1 4.5v.793c.026.009.051.02.076.032L7.674 8.51c.206.1.446.1.652 0l6.598-3.185A.755.755 0 0 1 15 5.293V4.5A1.5 1.5 0 0 0 13.5 3h-11Z" />
                  <path d="M15 6.954 8.978 9.86a2.25 2.25 0 0 1-1.956 0L1 6.954V11.5A1.5 1.5 0 0 0 2.5 13h11a1.5 1.5 0 0 0 1.5-1.5V6.954Z" />
                </svg>
                <input type="email" id="email" v-model="email" class="grow" placeholder="Email" />
              </label>
            </div>
            <div>
              <label class="input input-bordered flex items-center gap-2 w-[22rem]">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
                  <path fill-rule="evenodd" d="M14 6a4 4 0 0 1-4.899 3.899l-1.955 1.955a.5.5 0 0 1-.353.146H5v1.5a.5.5 0 0 1-.5.5h-2a.5.5 0 0 1-.5-.5v-2.293a.5.5 0 0 1 .146-.353l3.955-3.955A4 4 0 1 1 14 6Zm-4-2a.75.75 0 0 0 0 1.5.5.5 0 0 1 .5.5.75.75 0 0 0 1.5 0 2 2 0 0 0-2-2Z" clip-rule="evenodd" />
                </svg>
                <input type="password"  v-model="password" class="grow" placeholder="Password" />
              </label>
            </div>
            <div>
              <label class="input input-bordered flex items-center gap-2 w-[22rem]">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
                  <path fill-rule="evenodd" d="M14 6a4 4 0 0 1-4.899 3.899l-1.955 1.955a.5.5 0 0 1-.353.146H5v1.5a.5.5 0 0 1-.5.5h-2a.5.5 0 0 1-.5-.5v-2.293a.5.5 0 0 1 .146-.353l3.955-3.955A4 4 0 1 1 14 6Zm-4-2a.75.75 0 0 0 0 1.5.5.5 0 0 1 .5.5.75.75 0 0 0 1.5 0 2 2 0 0 0-2-2Z" clip-rule="evenodd" />
                </svg>
                <input type="password" v-model="confirmPassword" placeholder="Confirm Password" class="grow" />
              </label>
            </div>
  
            <div class="flex justify-center">
              <button type="submit" class="text-[1.5rem] mt-1 text-black bg-gradient-to-b from-[#00d6a8] to-[#00af89] h-[3rem] w-[15dvw] rounded-[50rem] hover:bg-gradient-to-b hover:from-[#00af89] hover:via-[#008c73] hover:to-[#006e5c] transition-all duration-300">
                สมัครสมาชิก
              </button>
            </div>
            <div class="flex justify-center">
              <div class="flex gap-7 mt-2">
                <div>
                  <img class="w-[3rem] h-[3rem]" src="../img/social1.png" alt="" />
                </div>
                <div>
                  <img class="w-[3rem] h-[3rem]" src="../img/social2.png" alt="" />
                </div>
                <div>
                  <img class="w-[3rem] h-[3rem]" src="../img/social3.png" alt="" />
                </div>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
</template>
  
  <script>
  import { RouterLink } from 'vue-router';
  
  export default {
    data() {
      return {
        username: '',
        email: '',
        password: '',
        confirmPassword: '',
      };
    },
    methods: {
      handleSignUp() {
        if (this.username && this.email && this.password && this.password === this.confirmPassword) {
          
          this.$router.push('/');
        } else {
          alert('กรุณากรอกข้อมูลให้ครบถ้วนและตรวจสอบรหัสผ่าน');
        }
      },
    },
  };
  </script>
  