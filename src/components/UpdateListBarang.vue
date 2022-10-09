<template>
    <div class="container">
        <div class="my-4">
            <h4 class="my-auto">Update Buku</h4>
        </div>
        <b-form @submit="onUpdate" v-if="show" class="border p-4">
            <b-form-group id="input-group-2" label="Judul:" label-for="input-2">
                <b-form-input id="input-2" v-model="form.namaBarang" placeholder="Masukan Judul Buku" required
                    class="mb-3">
                </b-form-input>
            </b-form-group>

            <b-form-group id="input-group-1" label="ISBN:" label-for="input-1">
                <b-form-input id="input-1" v-model="form.harga" placeholder="Masukan ISBN" required class="mb-3">
                </b-form-input>
            </b-form-group>

            <b-form-group id="input-group-3" label="Penerbit:" label-for="input-3">
                <b-form-input id="input-3" v-model="form.stok" placeholder="Masukan Nama Penerbit" required
                    class="mb-3"></b-form-input>
            </b-form-group>

            <b-form-group id="input-group-4" label="Pembuat:" label-for="input-4">
                <b-form-input id="input-4" v-model="form.supplier.namaSupplier" placeholder="Masukan Nama Pembuat"
                    required class="mb-3"></b-form-input>
            </b-form-group>

            <div class="text-center">
                <b-button type="submit" variant="primary" class="mx-3">Update</b-button>
                <router-link to="/dashboard" class="navbar-brand">
                    <b-button variant="success" class="mx-3">Kembali</b-button>
                </router-link>
            </div>
        </b-form>
    </div>
</template>
  
<script>
import axios from "axios";
export default {
    data() {
        return {
            result: {},
            form: {
                harga: "",
                namaBarang: "",
                stok: "",
                id: 0,
                supplier: "",
            },
            show: true,
        };
    },
    mounted() {
        this.onLoad();
    },
    methods: {
        async onLoad() {
            const id = this.$route.params.id;
            const token = localStorage.getItem("token");
            const data = await axios.get(
                `http://localhost:8080/barang/find-by-id/${id}`,
                {
                    headers: {
                        Authorization: `Bearer ${token}`,
                    },
                }
            );
            console.log(data);
            const result = await (await data).data.data;
            console.log("ini result", result);
            this.form = result;
        },
        async onUpdate(event) {
            const id = this.$route.params.id;

            event.preventDefault();
            const token = localStorage.getItem("token");
            try {
                const data = await axios.put(
                    `http://localhost:8080/barang/update/${id}`,
                    this.form,
                    {
                        headers: {
                            Authorization: `Bearer ${token}`,
                        },
                    }
                );
                console.log("ini update", data);
                alert("data berhasil diupdate");
                this.$router.push("/dashboard");
            } catch (error) {
                alert("data gagal diupdate");
            }
        },
    },
};
</script>
  