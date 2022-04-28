<template>
  <div id="app">
    <!-- <div class="nav-count w-100">
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">Navbar</a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#">Home</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Link</a>
              </li>
              <li class="nav-item dropdown">
                <a
                  class="nav-link dropdown-toggle"
                  href="#"
                  id="navbarDropdown"
                  role="button"
                  data-bs-toggle="dropdown"
                  aria-expanded="false"
                >
                  Dropdown
                </a>
                <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                  <li><a class="dropdown-item" href="#">Action</a></li>
                  <li><a class="dropdown-item" href="#">Another action</a></li>
                  <li><hr class="dropdown-divider" /></li>
                  <li>
                    <a class="dropdown-item" href="#">Something else here</a>
                  </li>
                </ul>
              </li>
              <li class="nav-item">
                <a class="nav-link disabled">Disabled</a>
              </li>
            </ul>
            <form class="d-flex">
              <input
                class="form-control me-2"
                type="search"
                placeholder="Search"
                aria-label="Search"
              />
              <button class="btn btn-outline-success" type="submit">
                Search
              </button>
            </form>
          </div>
        </div>
      </nav>
    </div> -->
    <div class="col-12">
      <form @submit.prevent="save" class="m-3 d-flex">
        <div class="mb-3 w-25 col-form-label mx-5">
          <label for="inlineFormInput" class="sr-only">Username</label>
          <input
            type="text"
            class="form-control mb-2"
            id="inlineFormInput"
            v-model="nama"
            placeholder="Username"
          />
        </div>
        <div class="mb-3 w-25 col-form-label mx-5">
          <label for="inlineFormInput" class="sr-only">Email address</label>
          <input
            type="email"
            class="form-control mb-2"
            placeholder="conannia17@gmail.com"
            id="inlineFormInput"
            v-model="email"
          />
        </div>
        <!-- <div class="mb-3 w-25 col-form-label mx-5">
          <label for="inlineFormInput" class="sr-only">Password</label>
          <input
            type="password"
            class="form-control"
            placeholder="password"
            id="inlineFormInput"
            v-model="password"
          />
        </div> -->
        <div class="col-auto">
          <button  type="submit" class="btn btn-primary mb-2 mt-4">
            Submit
          </button>
        </div>
      </form>
    </div>
    <div class="mb-2"></div>
    <div class="tab">
      <table class="table table-border">
        <thead>
          <tr>
            <th>Nama</th>
            <th>Email</th>
            <th>Aksi</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(w, index) in wadah" :key="index">
            <td>{{ w.nama }}</td>
            <td>{{ w.email }}</td>
            <td>
              <button @click="hapus(index)" type="submit" class="btn btn-primary mb-2">
                Delete
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      nama: "",
      email: "",
      // password: "",
      wadah: [],
    };
    
  },
  methods: {
    save() {
      if (this.nama.trim() === "" || this.email.trim() === "") {
        return;
      }

      this.wadah.push({
        nama: this.nama,
        email: this.email,
      });
      (this.nama = ""), (this.email = "");
  //     // alert("save")
  //     // console.log(wadah)
    },
    hapus(index) {
      this.wadah.splice(index, 1);
    },
  },
};
</script>

<style>
</style>
