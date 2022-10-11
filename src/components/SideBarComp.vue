<template>
    <div>
        <div class="row">
            <b-col>
                <b-card footer-bg-variant="info" footer-text-variant="primary" footer-class="footer-card text-center"
                    class="shadow mb-2" footer-tag="footer">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT2paNURw1DBfUC5w4I3m3EoIo7vHLpWxtXCg&usqp=CAU"
                        alt="" class="w-100">
                    <template #footer>
                        <h6 class="mb-0 profile">{{profileName}}</h6>
                    </template>
                </b-card>
            </b-col>
        </div>

        <div class="row">
            <b-col>
                <b-card header="Menu" header-bg-variant="info" header-text-variant="primary"
                    header-class="header-card text-center" class="shadow mb-2 menu">

                    <ul class="nav nav-pills row">
                        <li class="active">
                            <a href="#1a" data-toggle="tab">Barang</a>
                        </li>
                        <li><a href="#2a" data-toggle="tab">Supplier</a>
                        </li>
                    </ul>
                </b-card>
            </b-col>
        </div>

        <div class="row">
            <b-col>
                <b-card header="Online" header-bg-variant="info" header-text-variant="primary"
                    header-class="header-card text-center" class="shadow mb-2">
                    <b-row class="online">
                        <b-col>
                            hari online
                        </b-col>
                        <b-col>:</b-col>
                    </b-row>

                    <b-row class="online">
                        <b-col>
                            waktu online

                        </b-col>
                        <b-col>: </b-col>
                    </b-row>
                </b-card>
            </b-col>
        </div>

    </div>
</template>
<script>
export default {
    data() {
        return {
            profileName: "",
        };
    },
    created() {
        this.profileName = localStorage.getItem("profileName");
    }
}
// const profileName = localStorage.getItem("profileName");
// console.log("ini profile", profileName)

</script>


<style scoped>
.nav-pills .active {
    background-color: #0d6efd;
    color: white;
}

a,
a:hover {
    color: inherit;
    text-decoration: inherit;
}


li {
    padding: 7px;
}

.online {
    font-size: 12px;
    margin-top: 10px;
    margin-bottom: 10px;

}

.card-body {
    padding: 12px;
    padding-top: 0px;
    padding-bottom: 0px;

}

.profile {
    text-transform: uppercase;
}
</style>

