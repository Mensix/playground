<script setup lang="ts">
import FullCalendar from '@fullcalendar/vue3'
import type { CalendarOptions } from '@fullcalendar/core'
import resourceTimelinePlugin from '@fullcalendar/resource-timeline'

const options = reactive<CalendarOptions>({
  schedulerLicenseKey: 'GPL-My-Project-Is-Open-Source',
  timeZone: 'UTC',
  slotLabelFormat: { hour: 'numeric', minute: '2-digit', hour12: false },
  plugins: [resourceTimelinePlugin],
  resourceAreaWidth: '5%',
  initialView: 'resourceTimeline',
  slotMinTime: '08:00:00',
  slotMaxTime: '20:00:00',
  slotDuration: '00:30:00',
  resources: [
    { id: 'isi1', title: 'ISI-1' },
    { id: 'isi2', title: 'ISI-2' },
    { id: 'isk', title: 'ISK' },
    { id: 'tm', title: 'TM' },
  ],
  eventContent(info) {
    return { html: info.event.title }
  },
  events: [
    { resourceId: 'isi1', title: 'Programowanie komponentowe<br>dr Marcin Ziółkowski<br>Wykład, Sala 3/31', start: '2023-12-08T09:30:00+00:00', end: '2023-12-08T10:15:00+00:00' },
    { resourceId: 'isi1', title: 'Programowanie komponentowe<br>dr Marcin Ziółkowski<br>Laboratorium, Sala 3/19', start: '2023-12-08T10:30:00+00:00', end: '2023-12-08T12:00:00+00:00' },
    { resourceId: 'isi1', title: 'Sieci Komputerowe<br>dr Dariusz Strzęciwilk<br>Wykład, Sala 3/82', start: '2023-12-08T14:00:00+00:00', end: '2023-12-08T15:30:00+00:00' },
    { resourceId: 'isi1', title: 'Paradygmaty Programowania<br>dr Krzysztof Malczewski<br>Wykład, Sala 3/40', start: '2023-12-08T15:45:00+00:00', end: '2023-12-08T17:15:00+00:00' },
    { resourceId: 'isi1', title: 'Techniki cyfrowe i podstawy systemów wbudowanych<br>dr hab. Michał Szymański<br>Wykład, Sala 3/40', start: '2023-12-08T17:30:00+00:00', end: '2023-12-08T19:00:00+00:00' },

    { resourceId: 'isi2', title: 'Programowanie komponentowe<br>dr Marcin Ziółkowski<br>Wykład, Sala 3/31', start: '2023-12-08T09:30:00+00:00', end: '2023-12-08T10:15:00+00:00' },
    { resourceId: 'isi2', title: 'Architektura Oprogramowania<br>dr Tomasz Świsłocki<br>Laboratorium, Sala 3/11', start: '2023-12-08T10:30:00+00:00', end: '2023-12-08T12:00:00+00:00' },
    { resourceId: 'isi2', title: 'Sieci Komputerowe<br>dr Dariusz Strzęciwilk<br>Wykład, Sala 3/82', start: '2023-12-08T14:00:00+00:00', end: '2023-12-08T15:30:00+00:00' },
    { resourceId: 'isi2', title: 'Paradygmaty Programowania<br>dr Krzysztof Malczewski<br>Wykład, Sala 3/40', start: '2023-12-08T15:45:00+00:00', end: '2023-12-08T17:15:00+00:00' },
    { resourceId: 'isi2', title: 'Techniki cyfrowe i podstawy systemów wbudowanych<br>dr hab. Michał Szymański<br>Wykład, Sala 3/40', start: '2023-12-08T17:30:00+00:00', end: '2023-12-08T19:00:00+00:00' },

    { resourceId: 'isk', title: 'Sieci Komputerowe<br>dr Dariusz Strzęciwilk<br>Wykład, Sala 3/82', start: '2023-12-08T14:00:00+00:00', end: '2023-12-08T15:30:00+00:00' },
    { resourceId: 'isk', title: 'Paradygmaty Programowania<br>dr Krzysztof Malczewski<br>Wykład, Sala 3/40', start: '2023-12-08T15:45:00+00:00', end: '2023-12-08T17:15:00+00:00' },
    { resourceId: 'isk', title: 'Techniki cyfrowe i podstawy systemów wbudowanych<br>dr hab. Michał Szymański<br>Wykład, Sala 3/40', start: '2023-12-08T17:30:00+00:00', end: '2023-12-08T19:00:00+00:00' },

    { resourceId: 'tm', title: 'Systemy Multimedialne<br>dr Krzysztof Malczewski<br>Wykład, Sala 3/6', start: '2023-12-08T09:45:00+00:00', end: '2023-12-08T10:30:00+00:00' },
    { resourceId: 'tm', title: 'Systemy Multimedialne<br>dr Krzysztof Malczewski<br>Laboratorium, Sala 3/6', start: '2023-12-08T10:30:00+00:00', end: '2023-12-08T12:00:00+00:00' },
    { resourceId: 'tm', title: 'Sieci Komputerowe<br>dr Dariusz Strzęciwilk<br>Wykład, Sala 3/82', start: '2023-12-08T14:00:00+00:00', end: '2023-12-08T15:30:00+00:00' },
    { resourceId: 'tm', title: 'Paradygmaty Programowania<br>dr Krzysztof Malczewski<br>Wykład, Sala 3/40', start: '2023-12-08T15:45:00+00:00', end: '2023-12-08T17:15:00+00:00' },
    { resourceId: 'tm', title: 'Techniki cyfrowe i podstawy systemów wbudowanych<br>dr hab. Michał Szymański<br>Wykład, Sala 3/40', start: '2023-12-08T17:30:00+00:00', end: '2023-12-08T19:00:00+00:00' },
  ],
  headerToolbar: {
    start: undefined,
    end: undefined,
  },
})
</script>

<template>
  <FullCalendar :options="options" />
</template>

<style>
.fc {
  width: auto;
  width: 400vw;
}

.fc-resource-timeline-divider + td {
  width: 400vw;
  overflow-x: scroll;
}
</style>
