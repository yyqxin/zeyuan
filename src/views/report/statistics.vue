<template>
	<div>
	<!-- 查询条件组件 -->
		<searchItem ref="searchDate" ></searchItem>
		<div style="width:100%;float:left;margin: 0px 78px 20px 0;">
				<el-button type="primary" @click="searchEvent()">查询</el-button>
				<!-- 导出是直接调用后台接口的 -->
				<el-button type="primary" @click="exportData()">导出</el-button>
	    </div>
		<!-- 列表 -->
		<el-table
	    :data="tableData"
	    border
	    style="width: 100%">
		    <el-table-column
		      prop="department"
		      label="部门"
		      width="180">
		    </el-table-column>
		    <el-table-column
		      prop="reason"
		      label="季节"
		      width="180">
		    </el-table-column>
		    <el-table-column
		      prop="totalNum"
		      label="调样总数量"
		      width="180">
		    </el-table-column>
		    <el-table-column
		      prop="confirmNum"
		      label="已确认面料数量"
		      width="180">
		    </el-table-column>
		    <el-table-column
		      prop="unconfirmNum"
		      label="未确认面料数量">
		    </el-table-column>		    
   		</el-table>
	</div>
</template>
<script>
    import searchItem from '../../components/search.vue'
	export default {
		data() {
			return {
				tableData: [{
			        department: 'COBB女童组',
			        reason: '2018冬',
			        totalNum: '4',
			        confirmNum:'0',
			        unconfirmNum:'4'
		        }, {
		             department: 'COBB女童组',
			        reason: '2018冬',
			        totalNum: '4',
			        confirmNum:'0',
			        unconfirmNum:'4'
		        }]
			}
		},
		components:{
			searchItem
		},
		methods: {
			getTableData(){
				//调用后台接口请求数据
			},
			//数据导出
			exportData(){
				//调用导出数据接口
			},
			//数据查询（根据选择的条件进行数据查询 --- 调接口）
			searchEvent(){
				console.log("this.start_date:"+JSON.stringify(this.$refs.searchDate.form))
			}
		}
	}

</script>
