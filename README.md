# University Advising Ontology Knowledge-Based System (KBS)

# Project Description
This project implements a small ontology-based Knowledge-Based System (KBS) for university academic advising.  
It models students, courses, and prerequisite relationships, and uses inference rules to determine course eligibility and recommend suitable next courses.

---

## Ontology Design

### Concepts (Classes)
-Student: Represents an individual enrolled in the university.
-Course: Represents an academic subject offered in the curriculum.

### Relationships (Properties)
- requires(Course → Course) : directed relationship defining prerequisite relationship  
- completed(Student → Course) : assertion that a student has successfully finished a course.
- eligibleFor(Student → Course) : An inferred relationship determining if a student meets all requirements for a specific course. 

---

## Inference Logic

It retrieves the set of prerequisites for a target course.
It compares this set against the student's set of completed courses.
If the intersection of these sets satisfies the prerequisites, the eligibleFor property is inferred as True.
For recommendations, it filters all courses the student hasn't taken and returns only those where eligibleFor is True.

---

## How to Run
Using Jupyter Notebook:
1. Ensure you have Python and Jupyter installed (pip install notebook).
2. Open your terminal/command prompt in the project folder.
3. Run jupyter notebook.
4. Open SelineAtieno-XYZ-ontology-kbs.ipynb.
5. Click Cell > Run All to see the dataset, demo, and results.

# How to run tests
The tests are integrated into the final cell of the Jupyter Notebook using the unittest framework. To run them manually within the notebook, ensure the TestKBS class is defined and execute the cell containing unittest.main(argv=[''], exit=False).





# Example output snippet (5–10 lines)
ELIGIBILITY CHECKS

Alice -> AI: (True, set())
Bob -> AI: (False, {'Machine Learning', 'Statistics'})
Carol -> AI: (False, {'Machine Learning', 'Statistics'})


RECOMMENDATIONS

Recommendations for Alice: ['AI', 'Databases']
Recommendations for Bob: ['Statistics']
Recommendations for Carol: ['Python', 'Statistics']

......
----------------------------------------------------------------------
Ran 6 tests in 0.006s

OK



# Repo structure tree
.
SelineAtieno-853-ontology-kbs/
│
├── README.md
└── SelineAtieno-853-ontology-kbs.ipynb

