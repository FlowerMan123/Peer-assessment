<template>
<div>
  <div class="progress">
	<div class="progress-bar progress-bar-success" role="progressbar"
		 aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
		 style="width: 33%;">
		<span>学生加入</span>
	</div>
	<div class="progress-bar progress-bar-info" role="progressbar"
		 aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
		 style="width: 33%; margin-bottom: 0px;">
		<span>设置分组</span>
	</div>
	<div class="progress-bar progress-bar-warning" role="progressbar"
		 aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
		 style="width: 34%;">
		<span>分组名单</span>
	</div>
</div>
<div  data-spy="scroll" data-target="#navbar-example" data-offset="0" style="height: 450px; overflow-x:hidden; position: relative; margin-top: 0px;">
<div class="panel panel-default" style="width: 1000px; text-align: center;">
<h3>分组名单</h3>
<div class="panel panel-default" style="width: 800px;margin-left: 100px;" v-for="group in groupData">
	<div class="panel-heading">
		<h3 class="panel-title">
			{{group.class_name}}
		</h3>
	</div>

	<table class="table table-bordered">
	<!-- 	<h3 class="panel-title">
			
		</h3> -->

		<thead>
			<tr>
				<th>组别</th>
				<th>学号</th>
				<th>姓名</th>
			</tr>
		</thead>
		<tbody>
			<tr v-for="info in group.groupinfo">
				<td>第{{info.group_id}}组</td>
				<td><tr v-for="member in info.group_membermsg">{{member.school_num}}</tr></td>
				<td><tr v-for="member in info.group_membermsg">{{member.name}}</tr></td></td>
			</tr>
			
		</tbody>
</table>
</div>
</div>
</div>
<div></div>
</div>	
</template>
<script type="text/javascript">
// import axios from 'axios'
import store from '@/store.js'
export default {
  data () {
    return {
      groupData: []
    }
  },
  created () {
    this.groupData = store.fetch('groupMsg')
  }
}
</script>
<style type="text/css"></style>