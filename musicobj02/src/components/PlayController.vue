<template>
	<div class="playController">
		<div class="left">
			<img :src="playlist[playCurrentIndex].al.picUrl"/>
			<div class="content">
				<div class="title">{{playlist[playCurrentIndex].name}}</div>
				<div class="tips">横划可以切换上下首歌</div>
			</div>
		</div>
		<div class="right">
			<svg class="icon" aria-hidden="true" @click="kai">
				<use xlink:href="#icon-bofang1"></use>
			</svg>
			<svg class="icon" aria-hidden="true" @click="ting">
				<use xlink:href="#icon-iconstop"></use>
			</svg>
			<svg class="icon" aria-hidden="true">
				<use xlink:href="#icon-liebiao1"></use>
			</svg>
		</div>
		<audio ref="audio" :src=" `https://music.163.com/song/media/outer/url?id=${playlist[playCurrentIndex].id}.mp3` "></audio>
	</div>
</template>

<script>
	import {mapState} from "vuex";
	export default {
		name:"playcontroller",
		computed:{
			...mapState(["playlist","playCurrentIndex"])
		},
		methods:{
			kai(){
				this.$refs.audio.play();
			},
			ting(){
				this.$refs.audio.pause();
			}
		}
	}
</script>

<style lang="less">
        .playController {
            background: #fff;
            width: 7.5rem;
            height: 1.2rem;
            position: fixed;
            left: 0;
            bottom: 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid #ccc;
        
            .left {
                display: flex;
                padding: 0 0.2rem;
        
                img {
                    width: 0.8rem;
                    height: 0.8rem;
                    border-radius: 0.4rem;
                }
        
                .content {
                    padding: 0 0.2rem;
        
                    .tips {
                        font-size: 0.2rem;
                        color: #999;
                    }
                }
            }
        
            .right {
                .icon {
                    width: 0.4rem;
                    height: 0.4rem;
                    margin: 0 0.2rem;
                }
            }
        }
</style>
