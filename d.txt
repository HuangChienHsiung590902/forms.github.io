{{include '../common/header.htm'}}
{{include '../common/nav.htm'}}
<template>
<div>
    <div class="row">
        <!-- #region name -->
        <div class="col-sm-3">
            <div class="mb-3">
                <label for="name" class="form-label">Name</label>
                <input type="text" class="form-control" id="name" v-model="username" placeholder="Name" required />
            </div>
        </div>
        <!-- #endregion -->
    <!-- #region name -->
    <div class="col-sm-3">
        <div class="mb-3">
            <label for="name" class="form-label">Name</label>
            <input type="text" class="form-control" id="name" v-model="username" placeholder="Name" required />
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
        mode:String,
        search:String,
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
