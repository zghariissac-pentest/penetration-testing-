
# FSMO Roles (Flexible Single Master Operations)

## 1. Why FSMO Roles Exist
- Multi-master replication limitations  
- Tasks requiring a single authoritative DC  

## 2. Forest-Level Roles
### Schema Master
- Controls schema changes  

### Domain Naming Master
- Manages domain additions/removals  

## 3. Domain-Level Roles
### PDC Emulator
- Time synchronization  
- Password updates  
- Backward compatibility  

### RID Master
- Allocates RID pools to DCs  

### Infrastructure Master
- Updates cross-domain group references  

## 4. When FSMO Issues Occur
- Role holder unavailable  
- Transfers vs seizures  

## 5. Best Practices
- Placement of roles  
- Monitoring and health checks  

## Summary
Quick recap of each role and why they are critical to AD.
