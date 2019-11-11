# Workflow Service - Model

## Data modell

```mermaid
classDiagram

class Schedule
Schedule : +String : title
Schedule : +String : cronTab
Schedule : +DateTime : startsAt
Schedule : +DateTime : endsAt
Schedule : +DateTime : lastRun
Schedule: +Boolean : active

class Workflow
Workflow : +String : title
Workflow: +Boolean : active

class Task
Task: +String : title
Task: +Boolean : active

class ScriptTask

class OCRTask

class FileTask

class DockerTask

Task <|-- ScriptTask
Task <|-- OCRTask
Task <|-- FileTask
Task <|-- DockerTask

Workflow "1" *-- "1..*" Task : Contains
Schedule "*" o-- "*" Workflow : Contains
```