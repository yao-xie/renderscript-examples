# Introduction #

API specification of rs\_time.rsh

# Details #

| **Function** | **Description** |
|:-------------|:----------------|
| rs\_time\_t rsTime(rs\_time\_t `*`timer); | Get time.       |
| rs\_tm `*`rsLocaltime(rs\_tm `*`local, const rs\_time\_t `*`timer); | Get Local time. |
| int64\_t rsUptimeMillis(void); | Return the current system clock in milliseconds. |
| int64\_t rsUptimeNanos(void); | Return the current system clock in nanoseconds. |
| float rsGetDt(void); | Return the time in seconds since function was last called in this script.|