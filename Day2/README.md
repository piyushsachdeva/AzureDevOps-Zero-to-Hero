# Day2 Azure Boards and Agile Project Management 📊 - Work in progress

## Azure DevOps Demo Generator


## Azure Boards Overview
Azure board is a project management tool to plan and track your work.

## Defining Teams and Work Items
### What is a Work Item:
A work item can track all types of activities. It could be a 
*  task to do
*  a bug to fix,
*  or some other issue.
  We can assign them to people and keep track of their progress.

## Azure Boards Processes

1) **Basic**: Choose Basic when your team wants the simplest model that uses Issues, Tasks, and Epics to track work.
2) **Agile**
3) **Scrum**
4) **CMMI**

The basic process contains three work item types:
- Epics: Group your more significant items into Epics such as Website updates, Cloud migration, CICD implementation
- Issues: Further divide your Epics into Issues such as Homepage, about us page, secure sign-in
- Task: Tasks are the smallest amount of work that can be assigned to someone, for example, designing a homepage header, standardizing fonts, and fixing the homepage css to make it mobile responsive.

![Basic Process](https://learn.microsoft.com/en-us/azure/devops/boards/get-started/media/about-boards/hierarchy-2.png?view=azure-devops)

<h1>Project Tasks</h1>

<details open>
  <summary class="epic">
    <span class="icon">👑</span>Epics
  </summary>
  <ul>
    <li>
      <details open>
        <summary class="epic">
          <span class="icon">👑</span>Website Updates
        </summary>
        <ul>
          <li>
            <details open>
              <summary class="issue">
                <span class="icon">📗</span>Homepage
              </summary>
              <ul>
               <li> <span class="icon">☑</span>Designing a homepage header </li>
                <li class="task">Designing a homepage header</li>
                <li> <span class="icon">☑</span>Standardizing fonts </li>
                 <li> <span class="icon">☑</span>Fixing the homepage CSS to make it mobile responsive </li>
              </ul>
            </details>
          </li>
          <li>
            <details open>
              <summary class="issue">
                <span class="icon">ℹ📗</span>About Us Page
              </summary>
              <ul>
                <!-- Add specific tasks for About Us Page -->
              </ul>
            </details>
          </li>
          <li>
            <details open>
              <summary class="issue">
                <span class="icon">📗</span>Secure Sign-In
              </summary>
              <ul>
                <!-- Add specific tasks for Secure Sign-In -->
              </ul>
            </details>
          </li>
        </ul>
      </details>
    </li>
    <li>
      <details open>
        <summary class="epic">
          <span class="icon">☁👑</span>Cloud Migration
        </summary>
        <ul>
          <!-- Add specific tasks for Cloud Migration -->
        </ul>
      </details>
    </li>
    <li>
      <details open>
        <summary class="epic">
          <span class="icon">👑</span>CICD Implementation
        </summary>
        <ul>
          <!-- Add specific tasks for CICD Implementation -->
        </ul>
      </details>
    </li>
  </ul>
</details>


</body>
</html>


## Defining Sprints

A sprint is the amount of time we have to complete our tasks. Sprints help keep us focused. At the end, we can have a short retrospective meeting to share what we've accomplished. After that, we can plan the next one.
 A sprint is typically two to four weeks long.
 
## Defining Features and Epics

## Using Boards with GitHub
## Dashboards in Azure Boards
