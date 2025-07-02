# Insights
<img width="1919" alt="企业微信截图_17512877882078" src="https://github.com/user-attachments/assets/6d8f06d2-389b-4dbc-921c-dd62442a699f" />  

## relationship

![image](https://github.com/user-attachments/assets/0058be0d-9150-4d61-bfe5-3cdf135070e0)


### Frames
Determining performance consumption

### Tracks
So much has been done in this frame

### Logs
A log of so many things done in this frame

### Callers
Select the function hierarchy

### Calless
What does the function selected in Tracks do next?

### Timers 
Highlight event,find instance in Tracks and open source in Visual Studio

## Performance Macros
### TRACE_CPUPROFILER_EVENT_SCOPE
Mark the CPU execution time of a code block

_TRACE_CPUPROFILER_EVENT_SCOPE is a performance analysis macro provided by UE based on its own trace system_
```
UWorld* UWorld::GetDuplicatedWorldForPIE()
{
    TRACE_CPUPROFILER_EVENT_SCOPE(UWorld::GetDuplicatedWorldForPIE);

    ......
}
```
### QUICK_SCOPE_CYCLE_COUNTER
Used to quickly measure the CPU code segment execution time

_QUICK_SCOPE_CYCLE_COUNTER is part of the UE statistics system_
```
UWorld* UWorld::DuplicateWorldForPIE(const FString& PackageName, UWorld* OwningWorld)
{
	QUICK_SCOPE_CYCLE_COUNTER(STAT_World_DuplicateWorldForPIE);

  ......
```
### SCOPE_SECONDS_COUNTER
Output a piece of code consuming time

```
double Duration = 0.0;
{
	SCOPE_SECONDS_COUNTER(Duration);

  ......
}
```

