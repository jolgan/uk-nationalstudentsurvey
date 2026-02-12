# NSS 2025 Provider Performance Power BI Dashboard

This project was completed as part of a data task using real NSS (National Student Survey) data collected from universities across the UK. The original dataset contained formatting issues, spacer rows that created null values, pre-aggregated theme rows, inconsistent data types, and missing benchmark values which would have led to misleading analysis if left untreated. This documentation demonstrates an end-to-end workflow from raw Excel data > Power Query transformation > logical data restructuring → interactive (and intuitive!) dashboard design.

### Tools Used

* Power BI, Power Query
* Excel

### Key data issues identified

* .xlsb file format incompatible with efficient Power BI loading
* Spacer rows creating null records in Power Query
* First row not structured as headers
* Pre-aggregated theme rows causing potential double counting
* 'Difference' column is numeric and incorrectly stored as string format
* Missing benchmark values for 'Overall UK' rows
* Absence of a usable Theme field for filtering

### Data preparation screenshots

Removing spacer rows in Power Query:
<img width="959" height="504" alt="Removing spacer rows in Power Query" src="https://github.com/user-attachments/assets/73c9b85b-a8dd-44a0-ba93-0c9329ee1278" />


Using 'First Row as Headers' feature to structure the table:
<img width="960" height="504" alt="Use First Row As Headers" src="https://github.com/user-attachments/assets/580de5f1-ce55-4ba2-b2ce-98e89449f3d4" />


Filtering out null and blank rows:
<img width="960" height="504" alt="Filtering out null values" src="https://github.com/user-attachments/assets/5633ed86-b59a-4782-bd22-1e875ef87a65" />
<img width="240" height="367" alt="Removing blank rows (Benchmark)" src="https://github.com/user-attachments/assets/579cf189-60fd-49f9-83e5-20a1fb07b0da" />
<img width="243" height="374" alt="Removing blank rows (Positivity measure)" src="https://github.com/user-attachments/assets/9563d5ff-ffe9-40f6-b06c-ab5c5c06eb64" />
<img width="248" height="464" alt="Removing excluded theme rows (Theme)" src="https://github.com/user-attachments/assets/23c74c0c-d5c0-4fc5-9de7-9d9ad65c7a62" />

Fixing string data type to decimal:\
<img width="276" height="458" alt="Fixing string data type to decimal" src="https://github.com/user-attachments/assets/30b0d0d8-6e69-47bf-9efc-1ef4c20068f5" />

Removing theme summary rows to prevent duplication:\
<img width="286" height="440" alt="Removing theme rows" src="https://github.com/user-attachments/assets/b8b41efb-9598-4532-b68f-f5a7c3de7c1b" />

Creating a custom 'Theme' column using question numbers:\
<img width="523" height="330" alt="Custom column for themes" src="https://github.com/user-attachments/assets/4af40684-03f3-426c-832d-0b73dca7cef4" />

Creating a conditional column for 'Relative Performance' (Above/Below benchmark; Average):
<img width="695" height="359" alt="Conditional column for relative performance" src="https://github.com/user-attachments/assets/cdf2fe21-0717-4f02-9e7b-ca5f2ca86c31" />

List of applied steps:\
<img width="166" height="160" alt="All applied steps" src="https://github.com/user-attachments/assets/c703cb58-0a8d-49a3-be2c-4febc9440739" />


### Key preparation/dashboarding decisions
* Instead of relying on pre-calculated theme rows in the dataset, themes were logically grouped as sets of individual questions to allow for more accurate slicer filtering and to prevent doubling-up on data, which would have inflated numbers
* Questions that didn't belong to a theme were given an additional grouping: 'Theme 0'


The dashboard was built to allow a stakeholder to have a birds-eye view of performance issues, and included the following elements:

- **4 slicers**: Search by _Provider_, _Theme_, _Subject_, and _Relative Performance_
- **1 table**: Sorted by lowest scoring questions to surface most prominent pain points
- **3 dynamic cards**: Displays the average positivity measure, count of questions below the benchmark, and the worst-performing question
- **1 bar chart**: Displaying average positivity by theme

### Value-adding details
* Conditional formatting to highlight benchmark performance in red (to highlight urgency) or green (to communicate growth)
* Reset button for slicers
* Colour-matching for branding and consistency
* Centre-aligning columns for visual comfort (before and after below)
<img width="501" height="82" alt="Uncentered table columns" src="https://github.com/user-attachments/assets/df62d427-7a2b-4767-8d9b-e7f8b6aeff6c" />
<img width="496" height="84" alt="Centered table columns" src="https://github.com/user-attachments/assets/6dce29a0-60fa-4ef0-9064-935bb553369b" />


# Link to [interactive dashboard](https://app.powerbi.com/view?r=eyJrIjoiNDk3Njc5ZTctOTk2Mi00OTkxLWI1MGMtMjMwYTM5NjZmOTE3IiwidCI6ImYzMzE3MDQxLTRjMzYtNDQ2Ni1iNmIzLTdiZDdjNTYxZWM3YyJ9&embedImagePlaceholder=true)
# Link to National Student Survey 2025 provider-level [source dataset](https://www.officeforstudents.org.uk/data-and-analysis/national-student-survey-data/download-the-nss-data/)
