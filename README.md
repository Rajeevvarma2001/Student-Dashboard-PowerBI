# Student Dashboard (Power BI)

An interactive Power BI report for tracking academic performance across departments and academic years: enrollment, unique students, GPA, graduation rate and faculty staffing.

## Open the report

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows). Use a recent release; the file was saved in the September 2026 version.
2. Clone or download this repository.
3. Open `Student_dashboard_interactive.pbix`.

The data model is imported into the file, so the report works without any external connection.

## Report pages

### 1. Overview

| Area | Visuals |
|---|---|
| KPI cards | Total Enrollment, Unique Students, Average GPA, Graduation Rate %, Total Faculty |
| Trends | Total Enrollment by Academic Year, Average GPA Trend, Student-Faculty Ratio Trend |
| Department comparison | Unique Students by Department, Graduation Rate % by Department |
| Detail | Department Scorecard table (Enrollment, Unique Students, Average GPA, Graduation Rate %) |
| Filters | Academic Year slicer, Department slicer, **Clear filters** button |

### 2. Department Details (drillthrough)

Right-click any department on the Overview page and choose **Drill through → Department Details** to see that department alone:

- KPI cards: Total Enrollment, Unique Students, Average GPA, Graduation Rate %
- Trend lines: Enrollment, Average GPA and Graduation Rate % by Academic Year
- **Back** button to return to the Overview

## Data model

Star schema with five tables:

| Table | Role |
|---|---|
| `EnrollmentTable` | Fact table: enrollment records, holds most measures |
| `FacultyTable` | Fact table: faculty headcount by department and year |
| `StudentsTable` | Student dimension |
| `DepartmentsTable` | Department dimension (`DepartmentName`) |
| `DimAcademicYear` | Academic year dimension (`AcademicYear`) |

### Measures

| Measure | Table |
|---|---|
| Total Enrollment | EnrollmentTable |
| Unique Students | EnrollmentTable |
| Average GPA | EnrollmentTable |
| Graduation Rate % | EnrollmentTable |
| Total Faculty | FacultyTable |
| Student Faculty Ratio | FacultyTable |

## Skills demonstrated

- Dimensional modelling (fact and dimension tables, shared year and department dimensions)
- DAX measures for KPIs, distinct counts and ratios
- Drillthrough pages with a back button
- Slicers, cross-filtering and a "Clear all slicers" button
- Consistent layout and theming (Fluent 2 base theme, 1920×1080 canvas)

## Repository layout

```
Student_dashboard_interactive.pbix   Power BI report and data model
docs/screenshots/                    Page screenshots (add overview.png, department-details.png)
```
