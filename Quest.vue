<template>
<div id="app">
    <form @submit="formSubmit">
        <h1>${title}</h1>
        <div class="row container">
            <!-- #region uuid -->
            <div class="col-sm-4" hidden>
                <div class="mb-3">
                    <label for="name" class="form-label">uuid</label>
                    <input type="text" class="form-control" id="uuid" v-model="uuid" disabled>
                </div>
            </div>
            <!-- #endregion -->
            <!-- #region name -->
            <div class="col-sm-3">
                <div class="mb-3">
                    <label for="name" class="form-label">Name</label>
                    <input type="text" class="form-control" id="name" v-model="UserName" placeholder="Name" required>
                </div>
            </div>
            <!-- #endregion -->
            <!-- #region Sex -->
            <div class="col-sm-2">
                <div class="mb-3">
                    <label for="sex" class="form-label">Sex</label>
                    <div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="radio" name="sex" id="M" value="M" v-model="sex">
                            <label class="form-check-label" for="inlineRadio1">M</label>
                        </div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="radio" name="sex" id="F" value="F" v-model="sex">
                            <label class="form-check-label" for="inlineRadio2">F</label>
                        </div>
                    </div>
                </div>
            </div>
            <!-- #endregion -->
            <!-- #region email -->
            <div class="col-sm-7">
                <div class="mb-3">
                    <label for="email" class="form-label">Email address</label>
                    <input type="email" class="form-control" id="email" v-model="email" placeholder="name@example.com">
                </div>
            </div>
            <!-- #endregion -->
            <!-- #region combox -->
            <div class="col-sm-5">
                <div class="mn-3">

                    <div style="margin-top: 20px;">
                        <label for="sele" class="form-label">Checkbox</label>
                        <div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="option1" v-model="ckBox">
                                <label class="form-check-label" for="inlineCheckbox1">1</label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="option2" v-model="ckBox">
                                <label class="form-check-label" for="inlineCheckbox2">2</label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="checkbox" id="inlineCheckbox3" value="option3" v-model="ckBox" disabled>
                                <label class="form-check-label" for="inlineCheckbox3">3 (disabled)</label>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!-- #endregion -->
            <!-- #region range -->
            <div class="col-sm-6">
                <label class="form-label">Range</label>
                <div style="border: dotted 1px red; padding: 10px;">
                    <div class="mb-3">
                        <label class="form-label">(1)您多常使用急救性或噴霧型藥物？ ${q1}</label><br>
                        <input type="range" class="form-range" id="q1" min='0' max='10' v-model="q1">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">(2)您多常使用急救性或噴霧型藥物？ ${q2}</label><br>
                        <input type="range" class="form-range" id="q2" min='0' max='10' v-model="q2">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">(3)您多常使用急救性或噴霧型藥物？ ${q3}</label><br>
                        <input type="range" class="form-range" id="q3" min='0' max='10' v-model="q3">
                    </div>
                    <div class="col-sm-2">
                        <div class="mb-3">
                            <label for="ACT分數" class="form-label">ACT分數</label>
                            <input type="text" class="form-control" id="ACT分數" v-model="act_sum" disabled>
                        </div>
                    </div>
                </div>
            </div>
            <!-- #endregion -->
            <div class="col-sm-12"></div>
            <!-- #region checkbox -->
            <div class="col-sm-4">
                <div class="mb-3">
                    <label for="sele" class="form-label">Checkbox</label>
                    <div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="option1" v-model="ckBox">
                            <label class="form-check-label" for="inlineCheckbox1">1</label>
                        </div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="option2" v-model="ckBox">
                            <label class="form-check-label" for="inlineCheckbox2">2</label>
                        </div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="checkbox" id="inlineCheckbox3" value="option3" v-model="ckBox" disabled>
                            <label class="form-check-label" for="inlineCheckbox3">3 (disabled)</label>
                        </div>
                    </div>
                </div>
            </div>
            <!-- #endregion -->
            <!-- #region radio -->
            <div class="col-sm-5">
                <div class="mb-3">
                    <label for="sele" class="form-label">radio</label>
                    <div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="option1" v-model="radioBTN">
                            <label class="form-check-label" for="inlineRadio1">1</label>
                        </div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="option2" v-model="radioBTN">
                            <label class="form-check-label" for="inlineRadio2">2</label>
                        </div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="option3" v-model="radioBTN">
                            <label class="form-check-label" for="inlineRadio2">3</label>
                        </div>
                        <div class="form-check form-check-inline">
                            <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio3" value="option4" v-model="radioBTN" disabled>
                            <label class="form-check-label" for="inlineRadio3">4 (disabled)</label>
                        </div>
                    </div>
                </div>
            </div>
            <!-- #endregion -->
            <div class="col-sm-12"></div>
            <!-- #region textarea -->
            <div class="col-sm-6">
                <div class="mb-3">
                    <label for="txtArea" class="form-label">文字框</label>
                    <textarea class="form-control" id="txtArea" rows="5">
                        UUID:${uuid}  
                        Q2:${q2}       Sex:${sex}
                        ${UserName}   ${email}    ${sele}     ${ckBox}      ${radioBTN}
                    </textarea>
                </div>
            </div>
            <!-- #endregion  -->
            <!-- #region button -->
            <div style="text-align: center;margin-top: 5px;">
                <button type="reset" class="btn btn-primary">Reset</button>
                <button type="submit" class="btn btn-success">Submit</button>
            </div>
            <!-- #endregion -->
        </div>
    </form>

</div>
</template>

<!-- #region VUE -->

<script>
module.exports = {
    el: "#app",
    delimiters: ['${', '}'],
    data() {
        return {
            title: "基本資料輸入",
            title1: 'title-1',
            title2: 'title-2',
            title3: 'title-3',
            uuid: "{{uuid}}", // 接收傳過來的uuid
            UserName: "",
            email: "xxx@gmail.com",
            sele: "",
            sex: "M",
            ckBox: [],
            radioBTN: [] | "0", // 預設值 0
            q1: 0,
            q2: 0,
            q3: 0,
            act_sum: 0,
        }
    },
    mounted() {
        // alert('hi')
    },
    methods: {
        formSubmit(e) {
            // 保持原先輸入的資料
            // e.preventDefault();

            axios.post('/w_basic', {
                    params: {
                        uuid: this.uuid,
                        username: this.UserName,
                        sele: this.sele,
                        email: this.email,
                        ckBox: this.ckBox,
                        radioBTN: this.radioBTN,
                        q2: this.q2,
                        sex: this.sex,
                    }
                })
                .then(response => (this.info = response))
                .then(response => res.redirect('/'))
                .catch(function (error) {
                    console.log(error);
                });
        }
    },
    watch: {
        q1: function (val) {
            this.act_sum = parseInt(this.q1) + parseInt(this.q2) + parseInt(this.q3);
        },
        q2: function (val) {
            this.act_sum = parseInt(this.q1) + parseInt(this.q2) + parseInt(this.q3);
        },
        q3: function (val) {
            this.act_sum = parseInt(this.q1) + parseInt(this.q2) + parseInt(this.q3);
        }
    },
}
</script>
<!-- #endregion -->
<!-- #region STYLE -->

<style>
.container {
    margin: 20px;
    /* border: 1px solid red; */
}

textarea {
    text-align: left;
}

* {
    /* margin: 5px; */
    /* 版面文字間隔 */
    margin-top: 0 !important;
    margin-bottom: 1 !important;
}
</style>
<!-- #endregion -->
