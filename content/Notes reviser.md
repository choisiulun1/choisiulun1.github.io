---
tags: [dataview]
aliases: []
---
- A-type:
```dataview
LIST FROM #-A
```

- B-type:
```dataview
LIST FROM #-B
```

- C-type:
```dataview
LIST FROM #-C
```

1 day before:

```dataview
	List
	 WHERE file.ctime >= date(yesterday) AND file.ctime<=date(today)
    sort file.created desc
```

6 days before:

```dataview
	List
	 WHERE file.ctime >= date(today-6d) AND file.ctime<= date(today-5d)
    sort file.created desc
```

30 days before

```dataview
	List
	 WHERE file.ctime >= date(today-31d) AND file.ctime<= date(today-30d)
    sort file.created desc
```

