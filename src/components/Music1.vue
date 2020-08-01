<template>
	<div>
		<header>
		<h1>The Music Player</h1>
	</header>
		<span></span>
		<button   @click="prev">
			<span class="fa fa-angle-left sign"></span>
		</button>
		
		<button v-if="song" @click="playSong">
			<span class="fa fa-pause"></span>
		</button>
		<button v-if="nosong" @click="playSong">
			<span class="fa fa-play"></span>
		</button>
		<button @click="next">
			<span class="fa fa-angle-right sign"></span>
		</button><br>
			<div class="playlist">
			{{currentSong}}
			</div>
 <audio controls ref="audio">
  <source  v-bind:src="currentSong" type="audio/mpeg">
</audio> 
	</div>
</template>

<script>
	export default{
		name:"Music1",
		data:()=>({
			Songlist:["Kalimba.MP3","Maid with the Flaxen Hair.mP3","Sleep Away.MP3",],
			currentSong:"",
			songIndex:0,
			isPlaying:false,
			song:false,
			nosong:true


			
		}),
		created(){
			this.song = false
			this.currentSong = this.Songlist[this.songIndex]
		},
		methods:{
			prev(){
				if(this.songIndex == 0){
					return;
				}

				this.songIndex = this.songIndex - 1
				this.currentSong = this.Songlist[this.songIndex]
				this.$refs.audio.load()
				

			},
			playSong(){
				if(this.isPlaying){
					this.$refs.audio.pause()
					this.song =false
					this.nosong = true
					this.isPlaying = false
					return;
				}
				this.currentSong = this.Songlist[this.songIndex]
				this.$refs.audio.play()
				this.song =true
					this.nosong = false
				this.isPlaying = true
				console.log(this.currentSong)
			},
			next(){
				if(this.songIndex == this.Songlist.length-1){
					return;
				}
				
				this.songIndex = this.songIndex + 1

		

				this.currentSong = this.Songlist[this.songIndex]
				this.$refs.audio.load()
				

		
			}


		}

	}


</script>
<style>
	button{
		background-color:#f0a6ca;
		color:black;
		margin:50px;
		border-radius: 5px;
		height:40px;
		width:50px;
		font-weight:bold;
	}
	span{
		font-size:30px;
		font-weight:bold;
	}
	.playlist{
		height:70px;
		width:300px;
		background:#f0a6ca;
		margin:auto;
		margin-top: 20px;
		color:black;
		font-family:Sofia;
		font-weight:bold;
		letter-spacing:3px;
		font-size:20px;
	}
	audio{
		visibility: hidden;
	}
	header{
		font-style:serif;
		font-size:25px;
		font-family:Sofia;

	}
	.sign{
		font-weight:bold;
		font-size:20px;
	}
</style>