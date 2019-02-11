<template>
  <div id="app">
	  <h1>Hello</h1>

		<datepicker
			v-model="showDate" 
			minimum-view="month" 
			maximum-view="month" 
			@change="setShowDate"
			format="MMMM yyyy"
		></datepicker>

		<button @click="show4Weeks()">Show 4 Week View</button>

		<p v-if="selectedDate">
			You have selected {{ this.selectedDate }}
		</p>

	  <hr />

	  <div class="calendar">
		<calendar-view
			:show-date="showDate"
			:date-data="dateData"
			className="theme-default"
			@show-date-change="setShowDate"
			@click-date="setSelectedDate"
			:starting-day-of-week="this.calendarDisplayPeriod == 'week' ? new Date().getDay() : 1"
			:display-period-uom="this.calendarDisplayPeriod"
			:display-period-count="this.calendarDisplayPeriod == 'week' ? 4 : 1"
		></calendar-view>
	  </div>		
  </div>
</template>

<script>
import CalendarView from "./components/CalendarView.vue"
import Datepicker from 'vuejs-datepicker'

export default {
	name: "CalendarDemoApp",
	components: {
		CalendarView,
		Datepicker
	},
	data: function() {
		return { 
			showDate: new Date(),
			selectedDate: false,
			calendarDisplayPeriod: 'week',
			dateData: {
				'2019-02-01': {
					'className': 'medium',
				},
				'2019-02-02': {
					'className': 'medium',
				},
				'2019-02-03': {
					'className': 'low',
				},
				'2019-02-04': {
					'className': 'low',
					'booking': true
				},
				'2019-02-05': {
					'className': 'high',
					
				},
				'2019-02-06': {
					'className': 'medium',
				},
				'2019-02-07': {
					'className': 'medium',
				},
				'2019-02-08': {
					'className': 'medium',
				},
				'2019-02-09': {
					'className': 'medium',
				},
				'2019-02-10': {
					'className': 'low',
					'rate': '£ Low'
				},
				'2019-02-11': {
					'className': 'low',
					'rate': '£ Low',
					'booking': true
				},
				'2019-02-12': {
					'className': 'high',
					'rate': '£ High'
				},
				'2019-02-13': {
					'className': 'medium',
				},
				'2019-02-14': {
					'className': 'medium'
				},
				'2019-02-15': {
					'className': 'medium'
				},
				'2019-02-16': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-17': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-18': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					},
					'booking': true
				},
				'2019-02-19': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-20': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-21': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-22': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-23': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-24': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-25': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-26': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-27': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-02-28': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-03-01': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-03-02': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-03-03': {
					'className': 'low'
				},
			}
			}
	},
	methods: {
		setShowDate() {
			const dt = new Date(this.showDate)
			this.calendarDisplayPeriod = 'month'
			this.showDate = dt
		},
		setSelectedDate(d) {
			this.selectedDate = new Date(d)
		},
		show4Weeks(d) {
			this.calendarDisplayPeriod = 'week'
			this.showDate = new Date()
		}
	},
}
</script>

<style lang="scss">
@import "../static/css/default.css";
@import "../static/css/holidays-us.css";

.calendar {
	display: flex;
	height: 80vh;
	width: 80vw;
	margin-left: 10vw;
}
</style>
