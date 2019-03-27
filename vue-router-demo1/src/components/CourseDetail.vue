
<template>
	<div class="container">
		<h2>班课{{ id }}详情页面</h2>
		<img :src="course.cover">
		<p>{{course.courseName}}</p>
		<p>{{course.courseClass}}</p>
		<div class="btn">
		<button class="btn" @click="finishCourse(course)">结束课程</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'CourseDetail',
	
	data() {
		return {
			id: this.$route.params.id,
			course: {}
		};
	},
	methods: {
		finishCourse: function(course) {
			var _this = this;
			this.$http.get('http://localhost:8080/api/course/' + this.id).then(function(response) {
				_this.course = response.data;
			});
	
			this.$http({
				method: 'put',
				url: 'http://localhost:8080/api/course',
				data: {
					courseId:_this.course.courseId,
					userId: _this.course.userId,
					courseName: _this.course.courseName,
					courseClass: _this.course.courseClass,
					cover: _this.course.cover,
					courseCode:_this.course.courseCode,
					finished: 1,
				
				}
                
			}).then(function() {
				alert('班课修改成功');
				 _this.$router.push('/');

			});
		}
	},
	created() {
		var _this = this;
		this.$http.get('http://localhost:8080/api/course/' + this.id).then(function(response) {
			_this.course = response.data;
		});
			
	},

};
</script>
	.btn{
		width: 120px;
		height: 40px;
		border: 1px solid #fff;
		background-color: rgb(0, 187, 221);
		border-radius: 20px;
		outline: none;
		color: #fff;
		font-size: 16px;
	}
<style scoped></style>