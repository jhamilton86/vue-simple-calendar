<template>
  <div id="app">
	  <h1>Hello</h1>

		<datepicker
			v-model="showDate" 
			:minimum-view="calendarDisplayPeriod == 'week' ? 'day' : calendarDisplayPeriod" 
			:maximum-view="calendarDisplayPeriod == 'week' ? 'day' : calendarDisplayPeriod" 
			@change="setShowDate"
			:format="calendarDisplayPeriod == 'week' ? 'dd MMMM yyyy' : 'MMMM yyyy'"
		></datepicker>

		<select name="calendar-date-period" v-model="calendarDisplayPeriod">
			<option value="month">Month</option>
			<option value="week">Week</option>
		</select>

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
			:display-period-uom="this.calendarDisplayPeriod"
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
			calendarDisplayPeriod: 'month',
			dateData: {
				'2019-01-01': {
					'className': 'medium',
				},
				'2019-01-02': {
					'className': 'medium',
				},
				'2019-01-03': {
					'className': 'low',
				},
				'2019-01-04': {
					'className': 'low',
					'booking': true
				},
				'2019-01-05': {
					'className': 'high',
					
				},
				'2019-01-06': {
					'className': 'medium',
				},
				'2019-01-07': {
					'className': 'medium',
				},
				'2019-01-08': {
					'className': 'medium',
				},
				'2019-01-09': {
					'className': 'medium',
				},
				'2019-01-10': {
					'className': 'low',
					'rate': '£ Low'
				},
				'2019-01-11': {
					'className': 'low',
					'rate': '£ Low',
					'booking': true
				},
				'2019-01-12': {
					'className': 'high',
					'rate': '£ High'
				},
				'2019-01-13': {
					'className': 'medium',
				},
				'2019-01-14': {
					'className': 'medium'
				},
				'2019-01-15': {
					'className': 'medium'
				},
				'2019-01-16': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-17': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-18': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					},
					'booking': true
				},
				'2019-01-19': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-20': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-21': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-22': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-23': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-24': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-25': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-26': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-27': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-28': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-29': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-30': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-31': {
					'className': 'low'
				},
			}
			}
	},
	methods: {
		setShowDate() {
			const dt = new Date(this.showDate)
			this.showDate = dt
		},
		setSelectedDate(d) {
			this.selectedDate = new Date(d)
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
