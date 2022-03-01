<script setup>
import BaseButton from './components/BaseButton.vue'
import BaseButton1 from './components/BaseButton.vue'
console.clear()
const testBtn = () => console.log('test#1');
const testBtn2 = (e) => console.log('test#2',e);
const testBtn3 = (e) => console.log('test#3',e);
const testBtn4 = (e) => console.log('test#4',e);
const testBtn5 = (e,n) => {console.log('test[5] >> จะแสดง $event ขึ้นก่อน / ตามด้วย 555');console.log('test#5',e,n)}
const testBtn6 = (vent,n) => {console.log('test[6] >> จะขึ้น 555 ก่อน / ตามด้วย $event');console.log('test#6',vent,n)}
const testBtnExtra = (e) => console.log('ExtraBtn',e);
</script>
 
<template>
<div>
    <button @click="testBtn">test-1</button><br><br>
    <button @click="testBtn2">test-2</button><br><br>
    <button @click="testBtn3()">test-3</button> 
    <!-- เพียงแค่เราใส่ () มันก็ undefined แล้ว เพราะไม่ได้กำหนดค่าใน handle param ซึ่งจะอ้างถึงโดย $event ใน param เพื่ออ้างถึง event แบบ manual เลย -->
    <br><br><p>กำหนด $event ใน param</p>
    <button @click="testBtn4($event)">test-4</button>
<br><br><hr>
    <!-- ลำดับ มีความสำคัญ ในการเล่นกับ event -->
    <p>ลำดับ มีความสำคัญ ในการเล่นกับ event</p>
    <!-- <button @click="testBtn5($event,555)">test-5</button> -->
    <button @click="testBtn6(555,$event)">test-6</button><br>
    <hr>
    <!-- ------------------------------------------------------- -->
    <div>
    <BaseButton1 buttonName='Click Me' @onClick="testBtn4($event)"/>
    </div>
    <div>
      <button @click="testBtn4($event)">Simple Button</button>
    </div>
</div>
</template>
 
<style>

</style>