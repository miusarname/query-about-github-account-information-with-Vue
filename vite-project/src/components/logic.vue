<script setup></script>

<template>
  <h2>Cuentas consultadas</h2>
  <form>
    <div class="mb-3">
      <label for="exampleInputEmail1" class="form-label">Username</label>
      <input
        v-model="newCount"
        type="text"
        class="form-control"
        id="exampleInputEmail1"
        aria-describedby="emailHelp"
      />
      <div id="emailHelp" class="form-text">
        Please enter a valid username otherwise it will not be displayed in the
        table
      </div>
    </div>
    <button @click="addCount" class="btn btn-primary">Submit</button>
  </form>
  <!-- Results table -->
  <table class="table">
    <thead>
      <tr>
        <th scope="col">Username</th>
        <th scope="col">Id</th>
        <th scope="col">Url de la api</th>
        <th scope="col">Name</th>
        <th scope="col">Repositories</th>
        <th></th>
      </tr>
    </thead>
    <tbody v-for="count in counts">
      <tr>
        <td v-text="count.login"></td>
        <td v-text="count.id"></td>
        <td v-text="count.url"></td>
        <td v-text="count.name"></td>
        <td v-text="count.public_repos"></td>
        <td><i @click="deleteCount(count.id)" class="bi bi-x-lg"></i></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  data() {
    return {
      newCount: "",
      counts: [],
    };
  },
  methods: {
    addCount(e) {
      e.preventDefault();
      if (this.newCount.length <= 1) {
        return alert("Escribe tu usuario");
      } else {
        fetch("https://api.github.com/users/" + this.newCount)
          .then((res) => res.json())
          .then((data) => {
            console.log(data);
            if (data.message == "Not Found") {
              return alert("Usuario no encontrado");
            } else {
              this.counts.push({
                login: data.login,
                id: data.id,
                url: data.url,
                name: data.name,
                public_repos: data.public_repos,
              });
              console.log(this.counts);
            }
          })
          .catch((err) => {
            return;
          });
      }
    },
    deleteCount(id) {
      this.counts = this.counts.filter((count) => count.id != id);
    },
  },
};
</script>
