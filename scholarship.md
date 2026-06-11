---
layout: main
title: Scholarship
# profile: false

profile:
  title: "Sample Materials"
  # image: /imgs/kgh-w-gemma.jpg

  blocks:
  - title: "Interactive Lecture Notes"
    items:
      - name: "Calculus II"
        details:
          - "[Area Between Curves](/E01-C10-AreaBetweenCurves-DoenetGraphs.html)"
          - "[Integration by Parts](/E02-C17-IntegrationByParts.html)"
  - title: "Assignments"
    items:
      - name: Mathematical Cryptology
        details:
          - "[Prove the Euclidean Algorithm](/assets/sample-teaching/UMN-5248-04-EuclideanAlgorithm.pdf)"
          - "[Brute Force Attacks on Hashing Algorithms](/assets/sample-teaching/UMN-5248-02-SHA512-DictionaryAttack.pdf)"
          - "[Euler's Theorem vs. Euclid's Algorithm](/assets/sample-teaching/UMN-5248-12-ModularInverses.pdf)"

  - title: "Lecture Slides"
    items:
      - name: "Calculus III"
        details:
          - "[Surface Integrals](/assets/sample-teaching/UMN-C3-W10-SurfaceIntegrals-Lecture.pdf)"

  - title: "Other Sample Materials"
    items: 
      - name: "Course Syllabi"
        details: "[Mathematical Cryptology](/assets/sample-teaching/UMN-5248-03-Syllabus.pdf)"

profile: false
---

# Scholarly Activity


<!-- ## Contribution to scholarly growth of students -->

<details class="collapsible-h2" open>
  <summary class="collapsible-title">
    Contribution to scholarly growth of students
  </summary>

  <details open class="students-collapsible">
    <summary>Present Students</summary>
    <div class="students">

      {% for student in site.data.students.present %}
      <div class="student-card">

        <div class="student-header">
          <span class="student-name">{{ student.name }}</span>
          <span class="student-status">
            {{ student.level }}, Expected {{ student.expected }}
          </span>
        </div>

        <div class="student-projects">
          {% for project in student.projects %}
          <div class="student-work">

            <div class="project-meta">
              <span class="project-type">{{ project.type }}</span>
              {% if project.status %}
                <span class="status">{{ project.status }}</span>
              {% endif %}
            </div>

            
            {% assign t = project.type | downcase %}

            {% if t contains "presentation" or t contains "talk" %}
              {% assign icon_class = "project-icon-presentation" %}
            {% elsif t contains "poster" %}
              {% assign icon_class = "project-icon-poster" %}
            {% elsif t contains "paper" %}
              {% assign icon_class = "project-icon-paper" %}
            {% else %}
              {% assign icon_class = "project-icon-paper" %}
            {% endif %}

            <div class="project-title {{ icon_class }}" data-type="student-project">
              {{ project.title | markdownify }}
            </div>

          </div>
          {% endfor %}
        </div>

      </div>
      {% endfor %}

    </div>
  </details>

  <details class="students-collapsible">
    <summary>Past Students</summary>
    <div class="students students-past">

      {% for student in site.data.students.past %}
      <div class="student-card past-student">

        <div class="student-header">
          <span class="student-name">{{ student.name }}</span>

          <span class="student-status">
            {{ student.level }}
            {% if student.university %}
              — {{ student.university }}
            {% endif %}
          </span>
        </div>

        {% if student.current-status %}
          <div class="student-outcome">
            Graduated: {{ student.graduated }}
          <br/>
            Current: {{ student.current-status }}
          </div>
        {% endif %}

        <div class="student-projects">
          {% for project in student.projects %}

            {% assign t = project.type | downcase %}
            {% if t contains "presentation" or t contains "talk" %}
              {% assign icon_class = "project-icon-presentation" %}
            {% elsif t contains "paper" %}
              {% assign icon_class = "project-icon-paper" %}
            {% else %}
              {% assign icon_class = "project-icon-paper" %}
            {% endif %}

            <div class="student-work">
              <div class="project-meta">
                <span class="project-type">{{ project.type }}</span>
              </div>

              <div class="project-title {{ icon_class }}" data-type="student-project">
                {{ project.title | markdownify }}
              </div>
            </div>

          {% endfor %}
        </div>

      </div>
      {% endfor %}

    </div>
  </details>
</details>


## Open Educational Resource Development
- `Coming Soon`

## Written Scholarship

### Published Works
- `Coming Soon`

### Works in Progress
- `Coming Soon`

### PhD Thesis
- `Coming Soon`

<details class="collapsible-h2">
  <summary class="collapsible-title">
    Presentations
  </summary>

  


<ul class="presentations-list">
  {% assign talks = site.data.presentations 
     | sort: "month" 
     | sort: "year" 
     | reverse %}

  {% for talk in talks %}
    <li class="presentation-item">

      <div class="presentation-entry">
        
        <strong>{{ talk.title }}</strong>


        <span class="presentation-meta">
          <span class="event">
            {{ talk.event }}
            {% if talk.event_type %} ({{ talk.event_type }}){% endif %}
          </span>
          — {{ talk.institution }}, {{ talk.city }}, {{ talk.state }}
          <span class="presentation-date">
            {{ talk.month }}/{{ talk.year }}
          </span>
        </span>


      </div>

    </li>
  {% endfor %}
  </ul>
</details>