<template>
	<view>
		<view>
			<image style="width: 100%;height: 330rpx;" :src="ner.img"></image>
		</view>

		<view style="background-color: #00BF45;width: 100%;height: 100rpx;margin-top: -1%;line-height: 100rpx;text-align: center;display: flex;justify-content: center;color: #FFFFFF;">
			<view style="font-size: 20px;font-weight: 800;">{{ner.name}}</view>
			<view style="margin-left: 5%;font-weight: 800;font-size: 35rpx;"> ￥{{ner.parice}}</view>
		</view>


		<view style="font-weight: 800;padding: 5%;">
			景点简介
		</view>
		<view style="padding: 3%;margin-top: -4%;color: #666666;line-height: 25px;">
			仅包含云台山门票120元+景区区间交通票60元—张。1、预定须知:电子票仅限在预定时选择的入园日期3天内必须使用(3天内不开始使用则不能再使用)，剩下的两日在预订时选择的入园日期开始至当年12月31日前使用。景区内各景点不限制游玩次数。2、本产品仅支持二代身份证验证入园，可至景区任意验票口，直接验证入园，方便快捷。因此请务必携带预定时填写的身份证验证入园，无其他取票方式。3、预定限制:因景区实名制要求，同—使用日期，—个身份证仅能预定—张门票，若多人入园，请分别用各自身份证下单，谢谢。
		</view>



		<view style="font-weight: 800;padding: 5%;">
			使用须知
		</view>
		<view style="padding: 3%;margin-top: -4%;color: #666666;line-height: 25px;">
			1、无需取票，凭身份证直接验证入园。2、入园时间:7:00-17:00(不需要取票，凭身份证直接验证入园）。3、补充说明:凭预定身份证在景区任意验票口直接验证入园，若遇订单信息问题(信息不对照、身份证无效等)，请拨打景区服务电话0391-7709920查询;电子票仅限在预定时选择的入园日期3天内必须使用(3天内不开始使用则不能再使用)，剩下的两日在预订时选择的入园日期开始至当年12月31日前使用。景区内各景点不限制游玩次数。
		</view>



		<!-- 立即购买 -->
		<view style="position: fixed;bottom: 0;width: 100%;">
			<button is-link @click="showPopup" style="background-color: #00BF45;color: #FFFFFF;border-radius: 0;">立即购买</button>
		</view>
		<!-- 立即购买 -->
		<van-popup :show="show" @close="onClose" position="bottom" custom-style="height: 60%;" closeable close-icon="close"
		 z-index='88'>
			<view style="margin: 5%;color: #00BF45;">请填写订购信息</view>
			<!-- 手机号 -->
			<view style="margin-left: 3%;">
				<van-cell-group>
					<van-field label='手机号' :value="phone" placeholder="请输入手机号" border="false" />
				</van-cell-group>
			</view>
			<!-- 手机号 -->
			<!-- <view style="margin-left: 7%;margin-top: 5%;"  is-link>选择时间</view> -->
			<view style="margin-left: 3%;" is-link @click="time">
				<van-cell-group>
					<van-field label='选择时间' :value="times" placeholder="请选择日期" border="false" />
				</van-cell-group>
			</view>
			<van-popup z-index='99' :show="shows" @close="onCloses" position="bottom" custom-style="height: 60%;">
				<van-datetime-picker type="date"
				  :value="currentDate"
				  @input="onInput"
				  :min-date="minDate"
				  :formatter="formatter"
				  @confirm='confirm'
				  @cancel='cancel'
				/>
			</van-popup>


			<!-- 订票数量 -->
			<view>
				<view style="display: flex;margin-left: 7%;margin-top: 5%;">
					<view style="width:25%;">订票数量</view>
					<van-stepper value="1" @plus="onChange" @minus='onminus' />
				</view>
				<view v-for='(item,index) in items' :key='index'>
					<view style="display: flex;margin-left: 7%;margin-top: 3%;">
						<view style="margin-top: 2%;">
							游客姓名{{index+1}}
						</view>
						<van-cell-group>
							<van-field :value="name" placeholder="请填写游客姓名" border="false" />
						</van-cell-group>
					</view>
					<view style="display: flex;margin-left: 7%;margin-top: 3%;">
						<view style="margin-top: 2%;">
							身份证号{{index+1}}
						</view>
						<van-cell-group>
							<van-field :value="card" placeholder="请输入手机号" border="false" />
						</van-cell-group>
					</view>
					
				</view>
			</view>
			<!-- 订票数量 -->

			<view>

				<view style="position: fixed;display: flex;bottom: 0;margin-left: 10%;">
					<view style="margin-top: 5%;">合计：{{ner.parice}}</view>
					<view>
						<button style="background-color:#00BF45;color: #FFFFFF;" @click="buy">立即购买</button>
					</view>

				</view>
			</view>

		</van-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				ner: '',
				show: false,
				shows: false,
				phone: '',
				items: [''],
				times: '',
				name:'',
				card:'',
				currentDate: new Date().getTime(),
				    minDate: new Date().getTime(),
				    
			}
		},
		methods: {
			buy(){
				var id =this.ner
				var data = {
					id :id.id,
					img :id.img,
					name :id.name,
					parice:id.price,
					len:this.items.length
				}
				uni.navigateTo({
					url: '../buy/buy?data=' + encodeURIComponent(JSON.stringify(data))
				})
			},
			onChange(event) {

				this.items.push('')
			},
			onminus() {
				this.items.splice(this.items.length - 1, 1)
			},
			onclick() {

			},
			showPopup() {
				this.show = true
			},

			onClose() {
				this.show = false
			},
			onCloses() {
				this.show = false
			},
			time() {
				this.shows = true
			},
			onInput(event) {
			     this.currentDate=event.detail
			    // });
			  },
			  cancel(){
				  this.shows = false
			  },
			  confirm(val){
				  this.shows = false
				  var timestamp = val.detail;//获取过来的时间戳
				  var date =new Date(timestamp);//转换成正确的时间
				  
				   var Y = date.getFullYear() +'年';//年
				  
				    var  M = (date.getMonth() +1 <10 ?'0' + (date.getMonth() +1) : date.getMonth() +1) +'月';
				  
				    var  D = date.getDate() +'日';
				  var time = Y+'-'+M+'-'+D//拼接到一块赋值然后输出就ok了
				  this.times = time
			  },
			      // 这个是组件转化时间的方法
			      formatter (type, value) {
			        if (type === 'year') {
			          return `${value}年`
			        } else if (type === 'month') {
			          return `${value}月`
			        } else if (type === 'day') {
			          return `${value}日`
			        } else if (type === 'hour') {
			          return `${value}时`
			        } else if (type === 'minute') {
			          return `${value}分`
			        } else if (type === 'second') {
			          return `${value}秒`
			        }
			        return value
			      }
		},
		onLoad(options) {
			var ner = JSON.parse(decodeURIComponent(options.data));
			console.log(ner)
			this.ner = ner
		}
	}
</script>

<style>

</style>
