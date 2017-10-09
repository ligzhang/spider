<template lang="html">
    <div class="version">
        <div class="vesionOne">
            <div class="versionLeft">
                <img src="../static/version.png" style="width:100px;height:100px"alt="">
            </div>
            <div class="versionRight">
                <div class="versionTop">
                    1.0
                </div>
                <div class="versionDown">
                    完成于2016年7月20日
                </div>
            </div>
        </div>
        <div class="versionTwo">
            <div class="versionLeft">
                <img src="../static/version.png" alt="">
            </div>
            <div class="versionRight">
                <div class="versionTop">
                    1.1
                </div>
                <div class="versionDown">
                    完成于2016年8月20日
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// import $ from 'jQuery'
// console.log($)
export default {

}
</script>

<style lang="css">
.vesionOne{
    display: flex;


}
 .versionTwo {
     display: flex;


 }
.versionRight {
    display: flex;
    flex-direction: column;
}
.versionDown {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-grow: 1;
}
.versionTop {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-grow: 1;
}

</style>
