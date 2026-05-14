![alt text](img/8.jpg)

### Reconstruction (ML module for street lighting reconstruction)

A project that combines data from [**Inventory**](Inventarisation.md) and [**MSL Mapping**](MSL.Mapping.md) to create a "digital twin" of urban lighting. The goal is to predict street illuminance and automatically select optimal options for reconstruction.

**Task:**
To develop a tool that would automatically:
- Predict illuminance in areas based on inventory data.
- Identify zones that do not comply with standards.
- Recommend optimal LED replacements for old luminaires.
- Calculate the economic effect and payback period of the reconstruction.
- Allow for the quick preparation of accurate documentation for tenders.

**Architecture and Stack:**
- **ML Model:** An **LightGBM** model was used to predict illuminance, trained on a dataset of 100k+ examples (mobile laboratory data + inventory).
- **Data:** Processing and matching of illuminance and inventory data by GPS coordinates.
- **Recommendation System:** A separate model recommended optimal LED analogues, power, and light distribution type (KSS).
- **Analytics:** A module for automatic calculation of economic efficiency and payback periods.
- **Report:** A module for generating calculation results as a report for inclusion in tender documentation.

**Result:**
- A model for predicting urban lighting was created, eliminating the need for expensive field measurements.
- The identification of problematic network sections was automated, allowing for the prioritization of reconstruction work.
- The company gained a significant competitive advantage in tenders due to the speed and accuracy of preparing project proposals.

**My Role:**
I acted as **technical lead** and was responsible for:
- Designing the solution's architecture.
- Developing data processing algorithms and creating the dataset for ML.
- Creating and integrating the recommendation model.
- Communicating with business stakeholders and preparing the methodology for tenders.
