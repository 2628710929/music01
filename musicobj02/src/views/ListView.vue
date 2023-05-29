<template>
	<div class="listView">
		<listviewtop  :playlist="music.playlist"></listviewtop>
		<playlist :playlist="music.playlist"></playlist>
	</div>
</template>

<script>
	import{ useRoute } from "vue-router";
	import{ onMounted,reactive } from "vue";
	import { getListview } from "@/api/index.js"
	import listviewtop from "@/components/ListViewTop.vue"
	import playlist from "@/components/PlayList.vue"
	export default {
		name:"listview",
		setup() {
			
			var route = useRoute();//当前路由器信息对象
			var music = reactive({
				list:[],
				playlist:{
					creator:{},
					tracks:[]
				}
			})
			
			onMounted(async()=>{
				const id = route.query.id;
				console.log(id);
				var res = await getListview(id);
				music.playlist = res.data.playlist;
				console.log(music.playlist);
				
			})
			
			return{
				music
			}
		},
		components:{
			listviewtop,
			playlist
		}
	}
</script>

<style>
</style>