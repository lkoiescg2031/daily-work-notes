---
date: "{{date}}"
tags:
  - "daily reports"
---
# {{date:YYYY년 MM월 DD일}} 업무 리포트

## [[<% tp.date.now("YYYY-HH-DD", -1) %>|이전 할 일 요약]]

### TO DO
```tasks
(status.type is TODO) AND (created before {{date}})

```

### DOING
```tasks
(status.type is IN_PROGRESS) AND (created before {{date}})
```

### DONE
```tasks
done AND (created before {{date}})
```

## 새로운 할 일  `BUTTON[create-new-feature]` `BUTTON[create-bug-report]` `BUTTON[create-meeting]`

```tasks
created on {{date}}
```

```meta-bind-button
style: primary
id: create-new-feature
label: "New Feature"
hidden: true
actions:
  - type: templaterCreateNote
    templateFile: "Templates/Task template.md"
    folderPath: Tasks/Features
```

```meta-bind-button
style: primary
id: create-bug-report
label: "Bug Report"
hidden: true
actions:
  - type: templaterCreateNote
    templateFile: "Templates/Task template.md"
    folderPath: Tasks/Bugs
```

```meta-bind-button
style: primary
id: create-meeting
label: "Meeting"
hidden: true
actions:
  - type: templaterCreateNote
    templateFile: "Templates/Task template.md"
    folderPath: Tasks/Meetings
```

## 일일 요약

### 티켓 처리 요약

#### 처리 중
```tasks
(status.type is IN_PROGRESS) AND (created on {{date}})
```


#### 처리 완료
```tasks
done AND (create on {{date}}) 
```


## 기타



[[<% tp.date.now("YYYY-HH-DD", +1) %>|다음 할 일]]