=================================
**FAQs**
=================================

1. What are the report parameters?
----------------------------------
Below is the list of report parameters and their significance in the reports. The reports are stored in the ``reports_human`` table.

.. list-table:: Report Parameters
   :widths: 25 25 25
   :header-rows: 1

   * - Report Parameter
     - Definition
     - Data Representation
   * - frequency
     - Frequency at which the report is generated
     - Day, Week or Month
   * - Interval_start
     - Time interval from when the data collection was started
     - Time stamp with time zone
   * - Interval_end
     - Time interval when the data collection was ended
     - Time stamp with time zone
   * - namespace
     - The namespace to which the resource belongs to
     - String
   * - pods_avg_usage_cpu_core_total
     - Average usage of the CPU cores in that namespace
     - Millicore
   * - pods_request_cpu_core_total
     - Total CPU request made by the namespace
     - Millicore
   * - pods_avg_usage_memory_total
     - Average memory used by a particular namespace
     - Megabytes[MB]
   * - pods_request_memory_total
     - Total memory requested by the namespace
     - Megabytes[MB]
   * - pods_limit_memory_total
     - Maximum limit for memory in that namespace
     - Megabytes[MB]
   * - volume_storage_request_total
     - Total volume requested by the namespace
     - Gigabytes[GB]
   * - persistent_volume_claim_capacity_total
     - Total capacity of the PVC in that namespace
     - Gigabytes[GB]
   * - persistent_volume_claim_usage_total
     - Average usage of the PVC in a particular namespace
     - Gigabytes[GB]

2. How to check for reports?
----------------------------
There are a few things that you should verify before checking for reports or logs:

- Verify the pod is in a completed state(This ensures that there was no error when the pod ran)
- Check for logs in the pod(This should show some values)

Once these 2 checks are done you can connect to a pod by either an OpenShift terminal or by port forwarding the pod. The PSQL DB should have 3 log tables and 1 reports_human table which will be populated with data.