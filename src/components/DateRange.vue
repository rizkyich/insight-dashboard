<template>
  <div class="date-range">
    <div class="icon-date">
      <img src="@/assets/pagecontent/calendar (1).png" alt="calendar">
      <p>Period</p>
    </div>

    <div class="date-picker">
      <date-range-picker
          ref="picker"
          opens="left"
          :locale-data="{ firstDay: 1, format: 'dd-mm-yyyy HH:mm:ss' }"
          :timePicker="false"
          :timePicker24Hour="false"
          :appendToBody="false"
          :ranges="ranges"
          :date-format="dateFormat"
          :alwaysShowCalendars="true"
          @update="updateValues"
          @toggle="checkOpen"
          v-model="dateRange"
      >
        <template v-slot:input="picker" style="min-width: 350px; border: none;">
          <div class="input-date">
            {{ formatDate(picker.startDate) | date }} - {{ formatDate(picker.endDate) | date }}

            <button class="toggle-date" >
              <img v-if="!dateOpen" src="@/assets/pagecontent/arrow-down-grey.png"/>
              <img style="width: 1rem; height: 1rem;" v-else src="@/assets/pagecontent/close.png"/>
            </button>
          </div>
        </template>
        <div slot="footer" slot-scope="data" class="footer-date">
          <div style="margin-right: auto">
            <button @click="data.clickApply" class="btn btn-primary btn-sm">Apply</button>
          </div>
        </div>
      </date-range-picker>

      
    </div>
  </div>
</template>

<script>
import DateRangePicker from 'vue2-daterange-picker'
import 'vue2-daterange-picker/dist/vue2-daterange-picker.css'

export default {
  components: { DateRangePicker },
  data: () => ({
    dateOpen: false,
    monthNames: ["January", "February", "March", "April", "May", "June",
        "July", "August", "September", "October", "November", "December"],
    dateRange: {
      startDate: new Date(),
      endDate: new Date(),
    },
    ranges: {
      'Yesterday': null,
      'Last 7 days': null,
      'Last 30 days': null,
      'This Month': null
    },
    minDate: null
  }),
  watch: {
    dateRange: {
      immediate: true,
      handler(newValue) {
        const {endDate} = newValue
        const dt = new Date(endDate)
        const temp = dt.setMonth(dt.getMonth() - 6)
        this.minDate = new Date(temp)
      }
    }
  },
  methods: {
    updateValues(values) {
      const {startDate, endDate} = values
      
      this.dateRange.startDate = startDate.toDateString()
      this.dateRange.endDate = endDate.toDateString()
    },
    toggleDate() {
      this.dateOpen = true
      this.$refs.picker.togglePicker(this.dateOpen)
    },
    checkOpen(show, event) {
      this.dateOpen = !this.dateOpen
      event(this.dateOpen)
    },
    formatDate(dt) {
        const month = this.monthNames[dt.getMonth()]
        const day = String(dt.getDate()).padStart(2, '0')
        const year = dt.getFullYear()
      
        return day + '\n'+ month  + '\n'+  + year
    },
    dateFormat (classes, date) {
        if (!classes.disabled) {
          classes.disabled = date.getTime() >= new Date()
        }
        return classes
      }
  },
  created() {
    const dt = new Date()
    dt.setHours(0,0,0,0)

    const yesterday = new Date()
    yesterday.setDate(yesterday.getDate() - 1)

    const lastSeven = new Date()
    lastSeven.setDate(lastSeven.getDate() - 7)

    const lastThirty = new Date()
    lastThirty.setDate(lastThirty.getDate() - 30)

    const monthStart = new Date(new Date(new Date().setDate(1)))

    this.dateRange.startDate = yesterday.toDateString()
    this.dateRange.endDate = yesterday.toDateString()

    this.ranges['Yesterday'] = [yesterday, yesterday]
    this.ranges['Last 7 days'] = [lastSeven ,yesterday]
    this.ranges['Last 30 days'] = [lastThirty, yesterday]
    this.ranges['This Month'] = [monthStart, dt] 
  }
}
</script>

<style scoped>
.date-range {
  width: 100%;
  height: 100%;
  background-color: var(--clr-white);
  box-shadow: var(--dark-shadow);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 13px 1rem;
}

.date-picker, .date-picker button, .input-date {
  display: flex;
  align-items: center;
}

.toggle-date {
  width: 20px;
  height: 20px;
  margin-left: 2rem;
}

.toggle-date button img {
  width: 20px;
  height: 20px;
}

.icon-date {
  display: flex;
  align-items: center;
}

.icon-date img {
  margin-right: 1rem;
}

.icon-date {
  font-size: 1rem;
  color: var(--clr-grey-8);
}

.header-date {
  padding: .5rem 1rem;
  height: 2rem;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.header-date button img {
  width: 1rem;
}

.footer-date {
  background-color: var(--clr-white);
  padding: 0.5rem;
  color: black;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-top: var(--border);
}

.date-range >>> .vue-daterange-picker .reportrange-text {
  border: none;
  font-size: 1rem;
  color: var(--clr-grey-3);
}

.date-range >>> .vue-daterange-picker .daterangepicker:after, .date-range >>> .vue-daterange-picker .daterangepicker:before {
  display: none;
}

.date-range >>> .vue-daterange-picker .daterangepicker .btn-primary {
  background-color: var(--clr-green-dark);
  padding: .5rem 3rem;
}

.date-range >>> .vue-daterange-picker .daterangepicker th {
  color: var(--clr-grey-2);
  margin-bottom: 1rem;
}

.date-range >>> .vue-daterange-picker .daterangepicker .ranges li.active {
  background-color: var(--clr-green-dark);
  color: var(--clr-white);
  font-weight: bold;
}

.date-range >>> .vue-daterange-picker .daterangepicker td, .date-range >>> .vue-daterange-picker .daterangepicker .ranges li {
  color: var(--clr-grey-2)
}

.date-range >>> .vue-daterange-picker .daterangepicker td.active, 
.date-range >>> .vue-daterange-picker .daterangepicker td.active:hover {
  background-color: var(--clr-green-light);
  color: var(--clr-green-dark);
  font-weight: 700;
}

.date-range >>> .vue-daterange-picker .daterangepicker td.in-range {
  background-color: var(--clr-green-light);
}

.date-range >>> .vue-daterange-picker .daterangepicker .calendars .calendars-container .left .calendar-table .table-condensed thead tr .next {
  display: none;
}

.date-range >>> .vue-daterange-picker .daterangepicker .calendars .calendars-container .right .calendar-table .table-condensed thead tr .prev {
  display: none;
}


.date-range >>> .vue-daterange-picker .daterangepicker.opensleft {
  right: -16px;
  top: 34px;
}

.date-range >>> .vue-daterange-picker .daterangepicker .calendars {
  flex-wrap: unset;
}
</style>