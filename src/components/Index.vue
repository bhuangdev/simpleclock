<template>
  <div class="hello">
    <div class="date">{{ date }}</div>
    <div class="time">{{ time }}</div>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data () {
    return {
      date: '',
      time: ''
    }
  },
  mounted(){
    var that = this;
    setInterval(
      function(){ 
        that.showTime(); 
      }, 1000
    );
  },
  methods:{
    showTime(){
      var myDate = new Date(); //实例一个时间对象；
      var year = myDate.getFullYear();   //获取系统的年；
      var month = myDate.getMonth()+1;   //获取系统月份，由于月份是从0开始计算，所以要加1
      var day = myDate.getDate(); // 获取系统日，
      var hour = myDate.getHours(); //获取系统时，
      var minute = myDate.getMinutes(); //分
      var second = myDate.getSeconds(); //秒
      
      this.date = month + '月' + day + '日';
      this.time = this.addZero(hour) + ':' + this.addZero(minute) + ':' + this.addZero(second);
    },
    addZero(data){
      if(Number(data) < 10){
        data = '0' + data;
      }
      return data;
    }
  }
}
</script>

<style scoped>
.hello{
  left:50px;
  right:50px;
  margin-top:5%;
}
.date{
  font-size:200px;
}
.time{
  font-size:250px;
}
</style>
