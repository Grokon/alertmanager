---
layout: default
title:  node_alerts
categories: alerts
---
<!-- This loops through the paginated posts -->
##   MEMORY 

###  HostOutOfMemory
      summary: Node memory is filling up (< 10% left)
      description: Node memory is filling up (< 10% left)

###  HostMemoryUnderMemoryPressure
      summary: The node is under heavy memory pressure. High rate of major page faults
      description: The node is under heavy memory pressure. High rate of major page faults

###  HightPhpMemory
      summary: "PHP uses HIGHT memory"
      description: "Docker PHP container memory usage is . Reported by instance of job


###  HostSwapIsFillingUp
      summary: Host swap is filling up
      description: Swap is filling up (>80%)


##  NETWORK 
  
###  HostUnusualNetworkThroughputIn
      summary: Host network interfaces are probably receiving too much data (> 100 MB/s)
      description: Host network interfaces are probably receiving too much data

###  HostUnusualNetworkThroughputOut
      summary: Host unusual network throughput out
      description: Host network interfaces are probably sending too much data (> 100 MB/s)

<!-- Pagination links -->
---
##   DISK

###  HostUnusualDiskReadRate
      summary: Host unusual disk read rate
      description: Disk is probably reading too much data (> 50 MB/s)

###  HostUnusualDiskWriteRate
      summary: Host unusual disk write rate
      description: Disk is probably writing too much data (> 50 MB/s)

###  HostOutOfDiskSpace
      summary: Host out of disk space
      description: Disk is almost full (< 10% left)

###  HostDiskWillFillIn4Hours
      summary: Host disk will fill in 4 hours
      description: Disk will fill in 4 hours at current write rate

###  HostOutOfInodes
      summary: Host out of inodes
      description: Disk is almost running out of available inodes (< 10% left)

###  HostUnusualDiskReadLatency
      summary: Host unusual disk read latency
      description: "Disk latency is growing (read operations > 100ms)


###  HostUnusualDiskWriteLatency
      summary: Host unusual disk write latency
      description: Disk latency is growing (write operations > 100ms)
 
###  LowDiskSpace
      summary: Less than 20% disk space left on
      description: Consider sshing into the instance and removing old logs, clean temp files, or remove old apt packages with `apt-get autoremove`

###  LowDiskSpace
      summary: Less than 10% disk space left on
      description: Consider sshing into the instance and removing old logs, clean temp files, or remove old apt packages with `apt-get autoremove`

###  NoDiskSpace
      summary: 1% disk space left on
      description: There's only 1% disk space left

###  HighInodeUsage
      summary: High number of inode usage on
      description: Consider ssh'ing into the instance and removing files or clean temp files

---
##   CPU

###  HostHighCpuLoad
      summary: Host high CPU load
      description: CPU load is > 80%

###  high_load
      summary: Instance under high load
      description: of job  is under high load (>5%).

###  high_cpu
      summary: "Instance under high cpu usage
      description:  of job has really high CPU usage for over 10m."

###  ProcessNearFDLimits
      summary: Instance  has > 80% open files"
      description:  of job has really high open files usage for over 10m.


###  ExtremelyHighCPU
      description: CPU use percent is extremely high on for the past 2 hours.
      summary: CPU use percent is extremely high on for the past 2 hours.

###  HighCPU
      description: CPU use percent is extremely high on for the past 2 hours.
      summary: CPU use percent is high on for the past 2 hours.

###  CPUOutlierDetectionOnPrd
      description: The CPU usage on is outside normal values over a 1h period
      summary: CPU use percent is unusually high compared with the rate of the last hour

---
##   NODE

###  HostPhysicalComponentTooHot
      summary: Host physical component too hot
      description: Physical hardware component too hot

###  HostNodeOvertemperatureAlarm
      summary: Host node overtemperature alarm
      description: Physical node temperature alarm triggered

###  HostRaidArrayGotInactive
      summary: Host RAID array got inactive
      description: RAID array is in degraded state due to one or more disks failures. Number of spare drives is insufficient to fix issue automatically.

###  HostRaidDiskFailure
      summary: Host RAID disk failure
      description: At least one device in RAID array on failed. Array  needs attention and possibly a disk swap
 
###  HostEdacCorrectableErrorsDetected
      summary: Host EDAC Correctable Errors detected
      description: has had correctable memory errors reported by EDAC in the last 5 minutes.

###  HostEdacUncorrectableErrorsDetected
      summary: "ost EDAC Uncorrectable Errors detected
      description: has had uncorrectable memory errors reported by EDAC in the last 5 minutes.

---
##   OTHER

###  HostSystemdServiceCrashed
      summary: "Host SystemD service crashed
      description: "SystemD service crashed

###  HostOomKillDetected
      summary: "Host OOM kill detected
      description: "OOM kill detected

###  HostNetworkReceiveErrors
      summary: "Host Network Receive Errors
      description: interfacehas encountered receive errors in the last five minutes.

###  HostNetworkTransmitErrors
      summary: "Host Network Transmit Errors
      description: interface has encountered transmit errors in the last five minutes.
