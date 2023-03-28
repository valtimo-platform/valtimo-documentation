# Job service

This service provides a way to change Timer Events withing the current process

### Changing Timer event date  

Job service provides two methods that allow for an update on the timer due date in the current process

```
${jobService.updateTimerDueDateByActivityId("2300-01-01T00:00:00Z","timer-id",execution)} 
${jobService.addOffsetInMillisToTimerDueDateByActivityId(1000,"timer-id",execution)};
```

"updateTimerDueDateByActivityId" - allows changing the date by passing it as "String", in the ISO 8601 format , as the
first parameter along with the timer event id and the current execution of the process as second and third parameters
respectively

"addOffsetInMillisToTimerDueDateByActivityId" - used to add an offset to the current set due date by providing the amount
to be added, by passing a positive number, or subtracted, with a negative number




