
# SmartCourse AI
### Personalized Course Recommendation and Career Skill Gap Analysis

SmartCourse AI is a student-focused application that combines a fuzzy-logic-based course recommendation system with a career-related skill gap analysis feature. It helps students explore suitable course options and identify skills they may need to develop for a selected career goal.

## 1. Problem Statement

Students may find it difficult to choose learning areas based on their academic performance, subject knowledge, interests, and learning preferences. They may also be unsure which skills to develop for a particular career goal.

SmartCourse AI addresses these needs through two complementary features: personalized course recommendations and predefined skill gap analysis.

## 2. Objectives

- Generate course recommendations using the existing fuzzy logic system.
- Consider student inputs to support course selection.
- Compare selected skills against a predefined list for a chosen career goal.
- Identify matched skills and missing skills.
- Suggest learning priorities based on the identified skill gaps.
- Present results through a simple web interface.

## 3. Key Features

### A. Fuzzy Logic-Based Course Recommendation

The existing recommendation engine uses fuzzy logic rules to process student inputs and generate course recommendations.

The project configuration includes 13 input factors, 92 fuzzy rules, and five course options.

### B. Career Skill Gap Analysis

Students choose a career goal and select skills they already know. The system compares those selections with a predefined skill list associated with that goal.

The result includes:
- Matched skills
- Missing skills
- Estimated skill coverage percentage
- Suggested next skills to focus on

The coverage percentage is a simple estimate based on the predefined list. It is not a validated measure of professional readiness.

### C. Web-Based Interface

The application provides a homepage, course recommendation form, results page, skill gap analysis page, and contact page.

## 4. Technologies Used

- **HTML:** Page structure
- **CSS:** Layout and styling
- **JavaScript:** Frontend interactions and API requests
- **Node.js and Express:** Web server and API endpoints
- **Python:** Skill gap analysis logic and existing recommendation-engine integration
- **Fuzzy Logic:** Rule-based course recommendation

## 5. System Workflow

### Course Recommendation Workflow

1. The student opens the recommendation form.
2. The student enters the requested information.
3. The application sends the input to the recommendation backend.
4. The existing fuzzy logic engine processes the input using its rules.
5. The application displays the generated course recommendations.

### Skill Gap Analysis Workflow

1. The student opens the Skill Gap Analysis page.
2. The student selects a career goal and existing skills.
3. The frontend sends the selections to the `/api/skill-gap` endpoint.
4. The backend calls the Python skill gap analyzer.
5. The analyzer compares the selected skills with the predefined skill list.
6. The application displays matched skills, missing skills, estimated coverage, and next steps.

## 6. Skill Gap Analysis Logic

Let:

- **K** = number of selected skills that match the predefined list
- **N** = total number of skills in that predefined list

The estimated coverage is calculated as:

Coverage (%) = (K / N) * 100

For example, if a career goal has five predefined skills and a student selects two matching skills, the estimated coverage is:

Coverage = (2 / 5) × 100 = 40%

This percentage represents list coverage only. It does not establish job readiness or proficiency in the selected skills.

## 7. Running the Project Locally

### Prerequisites

- Node.js and npm
- Python installed and available in the terminal
- Project dependencies installed

### Steps

1. Open a terminal in the project root folder.
2. Install the Node.js dependencies if they have not already been installed:

   ```bash
   npm install
   ```

3. Start the server in PowerShell:

   ```powershell
   npm.cmd start
   ```

4. Keep the server terminal running.
5. Open the application in a browser at:

   `http://localhost:3000/index.html`

6. Use the Recommendation page or Skill Gap Analysis page to explore the features.

Follow the existing project configuration if it uses a different startup command or dependency setup.

## 8. Project Structure

```text
course-recommendation-system/
├── frontend/
│   ├── index.html
│   ├── input.html
│   ├── result.html
│   ├── skill-gap.html
│   └── contact.html
├── server.js
├── recommendation_engine.py
├── recommendation_engine_backup.py
├── skill_gap_analyzer.py
├── package.json
└── readme.md
```

The backup recommendation engine file is retained separately. The files shown above describe the main components; additional project files may also be present.

## 9. Limitations

- Skill gap analysis depends on predefined skills for each career goal.
- Skill coverage does not measure actual skill proficiency.
- Course recommendations depend on the existing fuzzy logic rules and configured inputs.
- The application does not independently verify a student's skills or guarantee career outcomes.

## 10. Future Scope

- Add more career goals and carefully curated skill lists.
- Include skill proficiency levels rather than only selecting known skills.
- Provide learning resources for missing skills.
- Store student profiles and track learning progress.
- Evaluate recommendation quality using a defined test dataset.
- Improve the interface with visual progress indicators and additional accessibility support.

## 11. Conclusion

SmartCourse AI combines fuzzy-logic-based course recommendations with a career-oriented skill gap analysis feature. By presenting course suggestions and highlighting skills to develop, it provides students with a structured starting point for learning and career planning.
