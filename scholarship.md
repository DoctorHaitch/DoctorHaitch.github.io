---
layout: main
title: Scholarship
profile: false
---

# Scholarly Activity

## Contribution to scholarly growth of students
### Present Students
#### Graduate Students


<ul>
{% for student in site.data.students.present %}
  <li>
    <strong>{{ student.name }}</strong>
    <span class="status">({{student.level}}, Expected Completion: {{ student.expected }})</span>

    {% for project in student.projects %}
      <div class="student-work">
        <span class="project-type">{{ project.type }}</span>{% if project.status %} <span class="status">({{ project.status }})</span>{% endif %}
        <span data-type="student-project">
          {{ project.title | markdownify }}
        </span>
      </div>
    {% endfor %}

  </li>
{% endfor %}
</ul>

### Past Students
#### Graduate Students (*University of Minnesota, Mankato*)

<ul>
{% for student in site.data.students.past-graduate %}
  <li>
    <strong>{{ student.name }}</strong>
    <span class="status">({{student.level}}, Completion: {{ student.when }})</span>

    {% for project in student.projects %}
      <div class="student-work">
        <span class="project-type">{{ project.type }}</span> {% if project.status %} <span class="status">({{ project.status }})</span>{% endif %}
        <span data-type="student-project">
          {{ project.title | markdownify }}
        </span>
      </div>
    {% endfor %}

  </li>
{% endfor %}
</ul>

- **Brendan Schlader** (Summer, 2025)
    - Master's Thesis
        > [Spectral Theory and the Gelfand Transform](/assets/student-projects/2025-brendan-schlader-thesis.pdf)
        {: data-type="article"}
- **Hunter Wilmes** (Spring, 2024)
    - Alternate Plan Paper
        > [Topics in Frame Theory: Frames of Translates](/assets/student-projects/2024-hunter-wilmes-app.pdf)
        {: data-type="article"}
    - Defense Presentation
        > [Topics in Frame Theory: Frames of Translates](/assets/student-projects/2024-hunter-wilmes-presentation.pdf)
        {: data-type="presentation"}

#### Undergraduate Students (*University of Minnesota, Mankato*)
- **Isaac Wicklund** (Spring, 2026)
    - Independent Study
    - Capstone Project
        > [Graph-Theoretic and Linear Optimization Approaches to Boolean Logic Minimization](/assets/student-projects/2026-isaac-wicklund-capstone.pdf)
        {: data-type="article"}

#### Undergraduate Students (*University of Delaware*)

### Open Educational Resource Development
- `Coming Soon`

## Written Scholarship

### Published Works
- `Coming Soon`

### Works in Progress
- `Coming Soon`

### PhD Thesis
- `Coming Soon`

## Presentations

### At Professional Meetings
- `Coming Soon`

### Invited Lectures, Presentations, Symposia Presentations, etc.
- `Coming Soon`

### Presentations to Students
- `Coming Soon`