# Functional Requirements
- Storing key/value pair
- Key needs to be unique
- Key can only be primitive type i.e. integer/string (1024 chars) etc
- Value can be anything (complex object, primitive type etc)
- No requirement to search based on value
- Get/Put/Delete based on single key
- Optional TTL on each entry
Note: Requirement is not always rigid. Consider possible change in future.
# Capacity Requirements
- Support 1 billion key/value pair
- 2k QPS of writes (include create/update/delete)
- 100K QPS of reads
- Value size as upper bound 10KB
# Micro Services
Two micro services
- Write micro services
- Read micro services
# Assumptions
## Higher end machine
- 4GHZ CPU
- 8 Core CPU
- 128 GB RAM
- 2TB of local mounted HDD
- 1000 QPS of typical reads
- 200 QPS of typical writes
# Points to be taken care
- Hotspot on TTL
# Reference
https://www.youtube.com/watch?v=rhch2dZFcdM

