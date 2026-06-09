---
layout: main
title: Teaching
profile: false
---

<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

# Teaching Record

## Sample Teaching Materials

### Minnesota State University, Mankato

- **Math122**:  Calculus II
	- `Coming Soon` 

- **Math316**: Intermediate Analysis
	- `Coming Soon`

### University of Minnesota
- **Math 2473**: Integral Vector Calculus (~80 students)
  - Sample Lecture Notes [Week 10: Surface Integrals PDF](/assets/sample-teaching/UMN-C3-W10-SurfaceIntegrals-Lecture.pdf)
- **Math 5248**: Mathematical Cryptology and Number Theory (~30 students)
  - Syllabus [PDF](/assets/sample-teaching/UMN-5248-03-Syllabus.pdf)
  - Sample Project Assignments
    - Prove the Euclidean Algorithm [PDF](/assets/sample-teaching/UMN-5248-04-EuclideanAlgorithm.pdf)
    - Brute Force Attacks on Hashing Algorithms [PDF](/assets/sample-teaching/UMN-5248-02-SHA512-DictionaryAttack.pdf)
    - Euler's Theorem vs. Euclid's Algorithm [PDF](/assets/sample-teaching/UMN-5248-12-ModularInverses.pdf)

<details class="collapsible-h2" open>
  <summary class="collapsible-title">
    Current Courses
  </summary>

  {% for sem in site.data.teaching %}
  {% if sem.status=="current" %}
    <div class="student-card">
      
      <div class="student-header">
        <span class="student-name">{{ sem.semester }}</span>
		<span class="student-status">{{ sem.university }}</span>
      </div>

      <div class="student-projects">
        {% for course in sem.courses %}
          <div class="student-work">
  
			<div class="
				project-title 
				project-icon-course 
				project-level-{{ course.level }}
				">

				<strong>{{ course.code }}</strong>: {{ course.title }}
				{% for each in course.meta %}
          <span class="project-type project-meta">{{ each }}</span>
        {% endfor %}

				{% if course.level == "grad" %}
				<span class="course-level-label">Graduate</span>
				{% endif %}

			</div>

			{% if course.desc %}
				<div class="course-description">
				{{ course.desc }}
				</div>
			{% endif %}


			</div>

        {% endfor %}
      </div>
    </div>
  {% endif %}
  {% endfor %}
</details>

<details class="collapsible-h2">
  <summary class="collapsible-title">
    Detailed Teaching Record
  </summary>

  {% for sem in site.data.teaching %}
  {% if sem.status=="past" %}
    <div class="student-card">
      <div class="student-header">
        <span class="student-name">{{ sem.semester }}</span>
		<span class="student-status">{{ sem.university }}</span>
      </div>
      <div class="student-projects">
        {% for course in sem.courses %}
          <div class="student-work">
			<div class="
				project-title 
				project-icon-course 
				project-level-{{ course.level }}
				">
				<strong>{{ course.code }}</strong>: {{ course.title }}
				{% for each in course.meta %}<span class="project-type project-meta">{{ each }}</span>{% endfor %}
				{% if course.level == "grad" %}
				<span class="course-level-label">Graduate</span>
				{% endif %}
			</div>
			{% if course.desc %}
				<div class="course-description">
				{{ course.desc }}
				</div>
			{% endif %}
			</div>
        {% endfor %}
      </div>
    </div>
  {% endif %}
  {% endfor %}
</details>