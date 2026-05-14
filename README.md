# CPU Alert System (AWS Project)

## Overview

This project is used to monitor CPU usage of an EC2 instance and send an alert when CPU goes above 5%.

---

## Services Used

* EC2
* CloudWatch
* SNS (Email Notification)

---

## Configuration

* Metric: CPUUtilization
* Threshold: **5%**
* Time: 5 minutes
* Action: Send email using SNS

---

## How It Works

1. EC2 instance runs normally
2. CloudWatch monitors CPU
3. If CPU > 5%, alarm triggers
4. SNS sends email alert

---

## Testing the Alarm (Trigger)

Run below command in EC2 terminal:

```bash
yes > /dev/null &
```

 This will increase CPU usage
 After some time, alarm will go to **"In Alarm" state**
 You will receive an email alert

---

## Stop the CPU Load (Untrigger)

Press:

```bash
Ctrl + C
```

OR run:

```bash
killall yes
```

 CPU usage will come down
 Alarm will go back to **"OK state"**

---

##  Note

* Threshold is kept very low (5%) for testing
* In real projects, use higher value like 70% or 80%

---

## Result

* Alarm triggered successfully when CPU increased
* Email notification received
* Alarm returned to normal after stopping process

---

## Conclusion

This project shows how to monitor EC2 CPU and get alerts using AWS CloudWatch and SNS.
