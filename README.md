# Inefficiency Detection in Photovoltaic Solar Plants

![Esta es una imagen](/Datos/Imagenes/featured.jpg)

- [Introduction](#introduction)
- [Objectives](#objectives)
- [Project results](#project-results)
    - [Insights (baseline)](#insights) 
    - [Actionable initiatives](#actionable-initiatives) 
- [Project structure](#project-structure)
- [Instructions](#instructions)

## Introduction <a name="introduction"></a>
The client is a renewable energy generation company that has detected anomalous behaviors in two of its photovoltaic solar plants. Their maintenance subcontractor is unable to identify the reasons for the inefficiencies and they wish to perform an in-depth analysis of the plants’ sensor and meter data before mobilizing their engineering team.

- [See a technical explanation of the project here.](https://pedrocorma.github.io/project/3ecommerce/)

## Objectives <a name="objectives"></a>
1. Analysing the available data to try to figure out where the problems may be and whether or not it is necessary to send a engineering team to the plants.

## Project results  <a name="project-results"></a>
### Insights (baseline)  <a name="insights"></a>
After a detailed analysis of the data from the photovoltaic solar plants it can be concluded that:
1. There are serious data quality problems. The part of the chain where these problems are generated, including the plant meters, should be reviewed.
2. The fact that the DC generation is about 10 times higher in plant 1 than in plant 2, added to the fact that the efficiency in plant 1 is above 10% leads to think that the DC generation data in plant 1 may be artificially scaled for some reason.

In the absence of further necessary checks, and assuming that the data are correct:
3. Both plants have received high amounts of irradiation, no problems have been located at this stage.
4. Although the ambient temperature is higher in Plant 2 and its modules are warmer than those of Plant 1, this does not seem to have a significant impact.
5. Plant 1’s DC generation works properly, the modules seem to bring DC to the inverters.
6. Plant 2’s DC generation does not work properly, some modules deliver very limited DC to the inverters even during peak irradiance hours.
7. DC to AC conversion of Plant 1 does not work well, it only transforms around 10% consistently. And this low efficiency is not due to moments of non-reception of DC nor is it concentrated in specific inverters, but it seems to be more structural (note that it could be due to data quality problems in the data regarding DC generation of Plant 1).
8. DC to AC conversion of plant 2 works properly, reaching efficiency levels up to 97%.

### Actionable initiatives  <a name="actionable-initiatives"></a>
1. Review data collection processes and their reliability.
2. Perform a maintenance inspection on the identified inverters of Plant 2 in which there are many moments of zero DC generation.
3. Perform a maintenance inspection of all inverters of the Plant 1.

## Project structure <a name="project-structure"></a>
- :file_folder: Datos
  - :file_folder: Imagenes:  Contains project images.
- :file_folder: Notebooks
  - `01_Diseño del proyecto.ipynb`: Notebook compiling the initial design of the project.
  - `02_Calidad de datos y creacion datamart analitico.ipynb`: Notebook creating analitic datamart (loading and unifying data, applying data quality processes, ...).
  - `03_Transformacion de datos.ipynb`: Feature engineering and data transformation notebook.
  - `03_Analisis e Insights.ipynb`: Notebook used for the execution of the exploratory data analysis and which collects the business insights found as well as the recommended actionable initiatives.

## Instructions  <a name="instructions"></a>
- Unzip ecommerce.rar and tablon_analitico.rar under 'Datos' folder.
- Remember to update the `project_path` to the path where you have replicated the project.
