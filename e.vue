{{include '../common/header.htm'}}
{{include '../common/nav.htm'}}
<template>
<div>
    <div class="row">
        <!-- #region name -->
        <div class="col-sm-3">
            <div class="mb-3">
                <label for="fname" class="form-label">Fname</label>
                <input type="text" class="form-control" id="fname" v-model="username" placeholder="First Name" required />
            </div>
        </div>
        <!-- #endregion -->
        <!-- #region name -->
        <div class="col-sm-3">
            <div class="mb-3">
                <label for="lname" class="form-label">Lname</label>
                <input type="text" class="form-control" id="lname" v-model="username" placeholder="Last Name" required />
            </div>
        </div>
        <!-- #endregion -->
    </div>

    text : ${mode} // ${search}
    <!-- 因為是用props接收資料的,所以只能用 ${} 處理資料 -->
    <ul type="none">
        <li v-for="(item,index) in data">${item.id}</li>
    </ul>
</template>

<script>
module.exports = {
    delimiters: ["${", "}"],
    props: {
        data: Object,
        mode: String,
        search: String,
    },
    emit: ["update"], // <---- try this
    data() {
        return {
            username: "XXX",
        };
    },
};
</script>

<style scoped>

</style>
