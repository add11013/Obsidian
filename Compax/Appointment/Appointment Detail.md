## Appointment type 
從 appointmentName取來
根據不同類別判斷後綴
``` java
private Optional<String> contractType(boolean hasBroadband, boolean hasTVBasePlan) {  
  if (hasBroadband && hasTVBasePlan) {  
    return Optional.of("BB & TV");  
  }  
  
  if (hasBroadband) {  
    return Optional.of("BB");  
  }  
  
  if (hasTVBasePlan) {  
    return Optional.of("TV");  
  }  
  
  return Optional.empty();  
}
```

## Job instruction
從 appointmentDetailNote取來
從workflow 8277中觸發
``` java
getWfoJobInstruction(appointment.getSignUp()).ifPresent(info::setAppointmentDetailNote);

private Optional<String> getWfoJobInstruction(Long signUpId) {  
  if (signUpId == null) {  
    return Optional.empty();  
  }  
  
  return dWorkflowRepo.findAllByBySignUpAndWorkflow(signUpId, WorkflowConstants.WFO_SEND_REQUEST_WORKFLOW).stream()//  
                      .filter(dw -> StringUtils.isNoneBlank(dw.getCWorkflows().get(0).getPayload()))//  
                      .max(Comparator.comparing(DWorkflow::getId)).map(dw -> dw.getCWorkflows().get(0).getPayload());  
}
```
