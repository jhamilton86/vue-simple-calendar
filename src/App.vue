<template>
  <div id="app">
		<calendar-view
			:show-date="showDate"
			:date-data="dateData"
			className="theme-default"
			@show-date-change="setShowDate"
		/>
		
  </div>
</template>

<script>
import CalendarView from "./components/CalendarView.vue"
import CalendarViewHeader from "./components/CalendarViewHeader.vue"

export default {
	name: "CalendarDemoApp",
	components: {
		CalendarView,
		CalendarViewHeader,
	},
	data: function() {
		return { 
			showDate: new Date(),
			dateData: {
				'2019-01-01': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-02': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-03': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-04': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					},
					'booking': true
				},
				'2019-01-05': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-06': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-07': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-08': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-09': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-10': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					},
					'rate': '£ Low'
				},
				'2019-01-11': {
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					},
					'rate': '£ Low',
					'booking': true
				},
				'2019-01-12': {
					'className': 'high',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					},
					'rate': '£ High'
				},
				'2019-01-13': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
				'2019-01-14': {
					'className': 'medium',
					'weather': {
						'icon': 'sun',
						'text': '22°'
					}
				},
				'2019-01-15': {
					'className': 'medium',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
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
					'className': 'low',
					'weather': {
						'icon': 'cloud-rain',
						'text': '64%'
					}
				},
			}
			}
	},
	methods: {
		setShowDate(d) {
			this.showDate = d
		},
	},
}
</script>

<style lang="scss">
@import "../static/css/default.css";
@import "../static/css/holidays-us.css";

div#app {
	display: flex;
	height: 80vh;
	width: 80vw;
	margin-left: 10vw;
}
</style>
