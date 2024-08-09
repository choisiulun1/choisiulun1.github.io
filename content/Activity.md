
```dataviewjs

dv.span("** 😊 Mood  😥**")


const calendarData = {
    intensityScaleStart: 1,
    intensityScaleEnd: 10,
    colors: "mood",
    entries: []
}

for(let page of dv.pages('"Daily Notes"').where(p=>p.mood)){ 

    calendarData.entries.push({
        date: page.file.name, 
        intensity: page.mood,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
      
}

renderHeatmapCalendar(this.container, calendarData)

```




```dataviewjs

dv.span("**Learn ** 📚")


const calendarData = {
    intensityScaleStart: 1,
    intensityScaleEnd: 10,
    colors: "blue",
    entries: []
}

for(let page of dv.pages('"Daily Notes"').where(p=>p.ap)){ 

    calendarData.entries.push({
        date: page.file.name, 
        intensity: page.ap,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
      
}

renderHeatmapCalendar(this.container, calendarData)

```
