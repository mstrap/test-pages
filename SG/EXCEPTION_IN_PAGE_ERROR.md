# EXCEPTION\_IN\_PAGE\_ERROR

SmartGit has crashed due to EXCEPTION\_IN\_PAGE\_ERROR. This exception
occurs when Windows fails to read file due to a hardware fault.

Typical reasons are:

  - SmartGit was started from a network share and there was a network
    interruption or server went offline.
  - SmartGit was started from a removable storage which was
    disconnected.
  - SmartGit was started from a faulty disk.

Please check Windows Event Log near the time of crash - sometimes,
additional information will be available there.
