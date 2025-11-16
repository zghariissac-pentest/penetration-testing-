
# Active Directory Database and Replication

## 1. The AD Database (NTDS.dit)
- What the database stores  
- Structure of directory data  
- How objects and attributes are organized  
- Why NTDS.dit is critical  

## 2. Logical vs Physical Partitions
- Schema partition  
- Configuration partition  
- Domain partition  
- Application partitions  

## 3. SYSVOL
- Purpose of SYSVOL  
- What it stores (scripts, GPO data)  
- Replication via DFS-R  

## 4. Replication Model
- Multi-master replication  
- How DCs synchronize changes  
- Update sequence numbers (USN)  
- Replication metadata  

## 5. Replication Topology
- Sites and site links  
- Intra-site vs inter-site replication  
- Bridgehead servers  

## 6. Replication Conflicts
- How conflicts occur  
- Last Writer Wins model  
- Conflict resolution mechanism  

## Summary
Short recap of how AD stores data and keeps every Domain Controller synchronized.
