<template>
  <div class="form">
    <form>
      <div class="sign_alert" v-if="useralert">
        <span>Iltimos malumotlarni to'liq kiriting!</span>
      </div>
      <div class="sign_alert" id="sign_span_true" v-if="sign_submit">
        <span>Malumotlar kiritildi!</span>
      </div>
      <div>
        <label for="name">Name:</label>
        <input type="text" id="name" placeholder="Name" v-model="user.name" />
      </div>
      <div>
        <label for="email">Email:</label>
        <input
          type="text"
          id="email"
          placeholder="Email"
          v-model="user.email"
        />
      </div>
      <div>
        <label for="password" v-if="!PSpace">Password:</label>
        <label for="password" v-if="PSpace"
          >Bo'sh joy ishlatish mumkin emas!</label
        >
        <input
          type="password"
          id="password"
          placeholder="Password"
          v-model="user.password"
          @keyup="passwordSpace"
        />
      </div>
      <div>
        <label for="manzil">Manzil:</label>

        <input
          type="text"
          id="manzil"
          placeholder="Manzil"
          v-model="user.manzil"
          @keyup="manzilUp"
        />
      </div>
      <div class="check">
        <div>
          <label for="uz">O'zbek tili</label>
          <input type="checkbox" id="uz" value="uz" v-model="user.language" />
        </div>
        <div>
          <label for="ru">Rus tili</label>
          <input type="checkbox" id="ru" value="ru" v-model="user.language" />
        </div>
        <div>
          <label for="en">Ingliz tili</label>
          <input type="checkbox" id="en" value="en" v-model="user.language" />
        </div>
      </div>
      <div>
        <button id="submitUser" type="button" @click="submitUser">
          Kiritish
        </button>
      </div>
      <ul>
        <li v-for="uss in users" :key="uss">{{ uss }}</li>
      </ul>
      <div>
        <h1>{{ user.name }}</h1>
        <h1>{{ user.email }}</h1>
        <h1>{{ user.password }}</h1>
      </div>
    </form>
  </div>
  <div>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Ism</th>
          <th scope="col">Familiya</th>
          <th scope="col">Manzil</th>
          <th scope="col">Email</th>
          <th scope="col">Parol</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td>Larry</td>
          <td>the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: "SingIn",
  data() {
    return {
      user: {
        name: "",
        email: "",
        password: "",
        manzil: "",
        language: [],
      },
      users: [],
      PSpace: false,
      useralert: false,
      sign_submit: false,
    };
  },
  methods: {
    submitUser() {
      // const submitus =document.querySelector("#submitUser");
      if (
        (this.user.name != "" &&
          this.user.email != "" &&
          this.user.password.length >= 8 &&
          this.user.manzil != "",
        this.user.language.length >= 1)
      ) {
        const userr = JSON.stringify(this.user);
        const userrr = JSON.parse(userr);
        this.users.push(userrr);
        this.useralert = false;
        this.user.name = "";
        this.user.email = "";
        this.user.password = "";
        this.user.manzil = "";
        this.user.language = [];
        console.log(this.users);
        this.sign_submit = true;
        setTimeout(() => {
          this.sign_submit = false;
        }, 2000);
      } else {
        this.useralert = true;
      }
    },
    passwordSpace(e) {
      if (e.code === "Space") {
        this.PSpace = true;
      } else if (e.code != "Space") {
        this.PSpace = false;
      }
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 1rem auto;
  font-size: 20px;
}
form {
  display: inline-block;
  width: 30%;
  border-radius: 5px;
  padding: 1rem;
  background-color: rgba(0, 0, 0, 0.138);
}
label {
  display: block;
  margin-left: 1rem;
  font-size: 23px;
}
input {
  display: block;
  width: 90%;
  padding: 1rem;
  border: none;
  border-radius: 5px;
  margin: 1rem auto;
  font-size: 16px;
  color: rgb(12, 13, 13);
  background-color: rgb(255, 255, 255);
}
.check {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  width: 150px;
}
.check label {
  display: inline;
  /* margin-top: 2rem; */
}
.check input {
  display: inline;
  width: 20px;
  margin-left: 1rem;
  /* float: right; */
}
button {
  padding: 0.5rem 2rem;
  border: none;
  font-size: 20px;
  margin-left: 1rem;
  background: rgb(2, 228, 250);
  background: radial-gradient(
    circle,
    rgba(250, 101, 2, 0.958) 28%,
    rgb(249, 164, 6) 100%
  );
  color: white;
  border-radius: 5px;
  box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset,
    rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset,
    rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px,
    rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px,
    rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;
  margin: 0 1rem;
}
button:active {
  transform: scale(1.1);
}
.sign_alert {
  margin: 1rem;
  display: flex;
  justify-content: center;
  text-align: center;
  color: red;
  font-size: 30px;
  font-weight: 600;
  letter-spacing: 3px;
  background: rgb(246, 0, 0);
  background: radial-gradient(
    circle,
    rgba(246, 0, 0, 0.35) 0%,
    rgba(147, 125, 236, 0.2) 100%
  );
  border-radius: 5px;
}
.sign_alert span {
  animation: sign_alert 2s linear infinite;
}
@keyframes sign_alert {
  0% {
    transform: scale(0.9);
  }
  50% {
    transform: scale(1);
  }
  100% {
    transform: scale(0.9);
  }
}
#sign_span_true {
  padding: 2.5rem 0;
  color: white;
  background: rgb(0, 246, 194);
  background: radial-gradient(
    circle,
    rgba(0, 246, 194, 0.504359243697479) 0%,
    rgba(9, 242, 59, 0.5) 100%
  );
}
</style>
