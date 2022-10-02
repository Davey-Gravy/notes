Date: 20/10/2021
## Summary
- Define date and time classes are given
	- Can be political
- Reykjavik University
	- *Term Time* software
	- Teachers have lots of independence
- Optimize room usage, 
- COVID considerations
	- \# of people constraint
- Teacher-centric problem -> NP complete
- Student considerations added -> "NP insane"
### Formulation
- Hard constraints
	- class has one teacher, teach one class at a time
- Soft constraints
	- preferences from time, room location
- Two common objective functions
	- sum of hard + soft constraint violations
	- weighted sum of hard + soft constraint violations
- has used:
	- branch and bound
	- integer linear programming
	- mixed integer linear programming
### Implementation
Reykjavik Engineering MSc.
- 7 programs
- 17 courses
- 125 students
	- randomly assigned
- 4 time slots
- 5 rooms in each time slot
- binary variables for teacher and student
- maximize sum product of student preference and enrollment

Achieved 100% enrollment in core courses, 93% enrollment in elective courses
#### Pros
- less errors
- more efficient
- avoids resentment between teachers
## Discussion
Difficulty in expanding?
- article uses a different method for larger problem, finds near-optimal solution
