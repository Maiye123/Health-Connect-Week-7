# Health-Connect-Week-7
## Week 7 — Analytical Testing, Validation & Dashboard Refinement

### Overview

Week 7 focused on testing, refining and validating the Data Analytics outputs developed during Weeks 5 and 6.

Rather than rebuilding the previous analysis, the focus was on determining whether the existing KPIs, dashboard outputs and analytical findings remained accurate and consistent when re-tested against the underlying dataset.

### Week 7 Objectives

The Data Analytics track focused on:

- Validating key KPI calculations.
- Checking dashboard values against the underlying dataset.
- Re-testing important no-show findings.
- Testing whether key findings remained consistent across relevant segments.
- Identifying data and analytical limitations.
- Refining dashboard interpretation and presentation.
- Conducting cross-track validation with Data Science.
- Preparing validated analytical outputs for Week 8 integration.

### Testing & Validation

#### KPI Validation

The following core dashboard KPIs were independently validated:

| KPI | Result |
|---|---:|
| Total Appointments | 5,000 |
| Unique Patients | 1,696 |
| No-Show Rate | 48.46% |
| Attendance Rate | 46.28% |
| Cancellation Rate | 5.26% |

The validated figures matched the dashboard values.

### Analytical Validation

Key findings from the previous analysis were re-tested against the underlying dataset.

| Finding | Data Analytics Result |
|---|---:|
| Previous no-shows: 0 | 43.5% |
| Previous no-shows: 1 | 53.5% |
| Previous no-shows: 2 | 59.4% |
| Previous no-shows: 3+ | 68.8% |
| Booking lead time: 31–60 days | 60.5% |
| Reminder sent | 47.4% |
| No reminder | 51.4% |
| Distance ≥20 km | 57.3% |

These findings are descriptive associations and should not be interpreted as evidence of causation.

### 31–60 Day Lead-Time Validation

The 31–60 day lead-time pattern was tested across appointment types:

| Appointment Type | No-Show Rate |
|---|---:|
| Follow-up | 65.1% |
| Diagnostic Test | 59.6% |
| Specialist Consultation | 59.2% |
| General Consultation | 58.1% |

The elevated pattern remained present across all four appointment types rather than being concentrated in a single category.

### Data Science Cross-Track Validation

Data Science independently recomputed the main analytical findings. The patterns were closely replicated, although the Data Science comparison used Attended + No-Show records only (n = 4,737), excluding cancelled appointments.

This difference in denominator explains part of the numerical variation between the two sets of figures.

The cross-track validation helped confirm the consistency of the major analytical patterns while also highlighting the importance of clearly documenting calculation methodology.

### Week 7 Gender Investigation

Following a Data Science finding concerning differences in model performance across gender groups, the Data Analytics track conducted a descriptive gender-stratified analysis.

The following variables were examined by gender:

- Previous no-shows
- Booking lead-time band
- Reminder status
- Distance to clinic

The purpose of this analysis was to determine whether the observed analytical patterns differed across gender groups and to provide additional evidence for Data Science's model investigation.

Based on the analysis, two candidate interaction features were provided to Data Science for further testing:

- `gender × distance_to_clinic_km`
- `gender × reminder_sent`

The interaction features remain subject to Data Science model testing and should not be interpreted as validated model improvements until the retesting is completed.

### Dashboard Refinement

The Week 7 dashboard was refined to focus on validation and cross-track investigation rather than reproducing the complete Week 6 analysis.

The refinement includes:

- Gender-stratified analysis of key no-show variables.
- Clearer distinction between descriptive associations and model findings.
- Retention of validated Week 6 analytical outputs where they remained relevant.
- Documentation of data-quality and methodological limitations.
- Cross-track validation information supporting further Data Science testing.

### Data Quality & Limitations

The following limitations were documented during testing:

- 90 records have missing distance-to-clinic values.
- 60 records have missing waiting-time values.
- There is no explicit reason-for-no-show field in the dataset.
- The dataset does not identify which of the two HealthConnect clinic locations was used for an appointment.
- The supplied `booking_lead_days` field does not consistently match a direct calculation from the booking and appointment dates. The supplied field was retained rather than overwritten.

These limitations should be considered when interpreting the findings and during further model or solution development.

### Week 7 Cross-Track Contribution

**Track:** Data Analytics → Data Science

**Component tested:** Analytical findings and gender-stratified variables relevant to model development.

**Information received:** Data Science model-testing results and a request to investigate whether key variables behaved differently across gender groups.

**Testing performed:** Gender-stratified analysis of previous no-shows, booking lead time, reminder status and distance.

**Information provided:** Gender-stratified findings and two candidate interaction features.

**Next action:** Data Science to test `gender × distance_to_clinic_km` and `gender × reminder_sent`.

**Status:** Pending Data Science retest.

### Week 8 Readiness

Before Week 8, the remaining priorities are:

1. Complete the Data Science testing of the proposed gender interaction features.
2. Record the resulting test and retest outcomes.
3. Incorporate any validated cross-track changes into the final HealthConnect solution.
4. Finalise dashboard and documentation updates.
5. Preserve the documented analytical limitations and methodology for final integration.

## Key Takeaway

Week 7 moved the Data Analytics work from analysis and integration toward systematic testing and validation. Existing findings were re-tested rather than recreated, limitations were documented, and new gender-stratified analysis was provided to Data Science to support further model testing.
