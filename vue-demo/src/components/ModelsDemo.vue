<template>
    <h3>表单输入绑定</h3>
    <form>
        <label for=1>v-model默认: </label>
        <input type="text" v-model="msg" id=1></input>
        <p>你的输入是：{{ msg }}</p>

        <label for=2>v-model.lazy: </label>
        <input type="text" v-model.lazy="msg2" id=2></input>
        <p>你的输入是：{{ msg2 }}</p>


        <label for=4>v-model.trim: </label>
        <input type="text" v-model.trim="msg4" id="4"></input>
        <p>你的输入是：{{ msg4 }}</p>

        <label for="checkbox">你的选择：</label>
        <input type="checkbox" id="checkbox" v-model="checked"></input>
        <p>你的选择是： {{ checked }}</p>


    </form>

</template>


<script>
export default {
    data() {
        return {
            msg: "",
            msg2: "",
            msg4: "",
            checked: false
        };
    },

};

</script>