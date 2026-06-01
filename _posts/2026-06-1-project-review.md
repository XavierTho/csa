---
layout: post
title: OCS Project Review
permalink: /ocs-project-overview
---

## Overview
Since late March, I have been working as part of the team for the CS-pathway game for teaching students in a highly gamified, interactive manner.

## Work as Related to CS113

<h2>How CS113 Concepts Apply to Mission Tools</h2>

<p>
The table below explains CS113 concepts that are directly shown in the Mission Tools level.
Evidence comes from the code for the Mission Tools game level, including its data structures,
object-oriented design, AI challenge system, player interaction logic, and progress tracking.
</p>

<table>
<tr>
    <th>Term</th>
    <th>Brief Description</th>
    <th>How Used in Mission Tools</th>
</tr>

<tr>
    <td><b>Data Structures</b></td>
    <td>Ways of organizing and storing data so it can be used efficiently.</td>
    <td>Used throughout the level to store player data, desk data, challenge history, mission progress, and level objects.</td>
</tr>
<tr>
    <td>Collections</td>
    <td>Groups of related data items stored together in one structure.</td>
    <td>Used to group challenge prompts, question styles, desk knowledge, mission desk zones, and game object classes.</td>
</tr>
<tr>
    <td>Lists</td>
    <td>Ordered collections where items can be accessed by position.</td>
    <td>Used in arrays such as <code>CHALLENGE_QUESTION_STYLES</code>, <code>missionDeskZones</code>, <code>this.classes</code>, and dialogue lists.</td>
</tr>
<tr>
    <td>Sets</td>
    <td>Collections that store unique values without duplicates.</td>
    <td>Used with <code>new Set()</code> to track busy challenge states and completed mission stations without duplicates.</td>
</tr>
<tr>
    <td>Dictionaries/Maps</td>
    <td>Structures that store data as key-value pairs for fast lookup.</td>
    <td>Used with objects like <code>DESK_AI_KNOWLEDGE_BASE</code> and <code>CHALLENGE_PROMPT_TEXT</code>, plus <code>new Map()</code> for active desk challenges and question history.</td>
</tr>

<tr>
    <td><b>Algorithms</b></td>
    <td>Step-by-step processes used to solve problems or complete tasks.</td>
    <td>Used in challenge generation, answer evaluation, mission scoring, distance checking, and level transition logic.</td>
</tr>
<tr>
    <td>Searching</td>
    <td>The process of finding specific data within a collection.</td>
    <td>Used with methods like <code>find()</code>, <code>filter()</code>, and <code>some()</code> to locate desks, level selectors, player objects, and matching options.</td>
</tr>
<tr>
    <td>Algorithm Analysis</td>
    <td>The study of how efficient an algorithm is in time and memory usage.</td>
    <td>Used indirectly by limiting stored history with <code>CHALLENGE_RECENT_HISTORY_LIMIT</code> and trimming logs so memory usage does not grow forever.</td>
</tr>

<tr>
    <td><b>Object-Oriented Design</b></td>
    <td>A programming approach that organizes code into objects with data and behavior.</td>
    <td>Used by defining <code>GameLevelCsPath2Mission</code> as a class with its own state, methods, and level behavior.</td>
</tr>
<tr>
    <td>Abstraction</td>
    <td>Hiding complex details and showing only the important features.</td>
    <td>Used by helper methods such as <code>_buildChallengePrompt()</code>, <code>_restoreMissionScore()</code>, and <code>_syncMissionProgressBoard()</code> to hide complex logic behind clear method names.</td>
</tr>
<tr>
    <td>Encapsulation</td>
    <td>Keeping data and the methods that use it together inside an object.</td>
    <td>Used by storing mission state like <code>this._missionProgressCount</code>, <code>this._activeDeskChallenges</code>, and <code>this._missionCompletedStations</code> inside the level class.</td>
</tr>
<tr>
    <td>Inheritance</td>
    <td>Allowing one class to reuse or extend the features of another class.</td>
    <td>Used when <code>GameLevelCsPath2Mission</code> extends <code>GameLevelCsPathIdentity</code>, allowing this level to reuse behavior from the parent class.</td>
</tr>
<tr>
    <td>Polymorphism</td>
    <td>Allowing different objects to use the same method in different ways.</td>
    <td>Used through game classes like <code>Player</code>, <code>FriendlyNpc</code>, and <code>GamEnvBackground</code>, which are all added to <code>this.classes</code> with different data and behavior.</td>
</tr>
<tr>
    <td>Design Patterns</td>
    <td>Reusable solutions to common software design problems.</td>
    <td>Used through factory-style helper functions like <code>createGatekeeperData()</code> and <code>createHiddenMissionDesk()</code> to create similar NPC/desk objects consistently.</td>
</tr>

<tr>
    <td><b>Software Development</b></td>
    <td>The process of planning, building, testing, and improving software.</td>
    <td>Represented through the SDLC desk, which teaches issues, commits, building, testing, integration, and agile development inside the game.</td>
</tr>
<tr>
    <td>Version Control</td>
    <td>A system for tracking and managing changes to code over time.</td>
    <td>Included as part of the Archivist and SDLC desk knowledge, where students are asked about Git, commits, repositories, forks, templates, and upstream remotes.</td>
</tr>
<tr>
    <td>Testing</td>
    <td>Checking software to make sure it works correctly and reliably.</td>
    <td>Included in the SDLC Master desk questions, which teach unit testing, integration testing, local tests, and CI checks.</td>
</tr>
<tr>
    <td>Build Tools</td>
    <td>Tools that help prepare, organize, and run a software project.</td>
    <td>Included in desk questions about build steps, running <code>make</code>, and confirming builds before committing or syncing.</td>
</tr>
<tr>
    <td>Debugging</td>
    <td>The process of finding and fixing errors in code.</td>
    <td>Used through <code>console.log()</code> and <code>console.warn()</code> statements that help track restored scores, desk reactions, and challenge evaluation failures.</td>
</tr>
<tr>
    <td>API Development</td>
    <td>Creating interfaces that allow different parts of software to communicate.</td>
    <td>Used when the level calls <code>AiChallengeNpc.requestAiText()</code> to generate questions and evaluate student answers through an AI interaction system.</td>
</tr>
<tr>
    <td>Database Integration</td>
    <td>Connecting software to a database to store, retrieve, and update data.</td>
    <td>Used indirectly through <code>ProfileManager</code>, which restores and saves mission progress such as score, completed stations, and mission progress count.</td>
</tr>

<tr>
    <td>CI/CD</td>
    <td>A workflow for automatically testing, building, and deploying code changes.</td>
    <td>Included as a learning topic in the SDLC Master desk, where students are asked about continuous integration and why it matters.</td>
</tr>

<tr>
    <td><b>Documentation</b></td>
    <td>Written explanations that help people understand and use a project.</td>
    <td>Used through comments that label sections of the file, such as background setup, player setup, assessment portal logic, and private helper methods.</td>
</tr>
<tr>
    <td>Code Comments</td>
    <td>Notes written inside code to explain how certain parts work.</td>
    <td>Used throughout the file to organize sections like <code>Prompt templates</code>, <code>Desk Knowledge Base</code>, <code>Background</code>, <code>Player</code>, and private methods.</td>
</tr>
<tr>
    <td>Help System</td>
    <td>Guidance built into a project to help users understand what to do.</td>
    <td>Used through NPC greetings, zone messages, toast alerts, and dialogue prompts that tell players to move to desks, click, press E, and answer challenges.</td>
</tr>

<tr>
    <td><b>Personal/Social Relevance</b></td>
    <td>The connection between a project and its impact on people or communities.</td>
    <td>The level is designed to teach students CS pathway skills through interactive missions, beginner-friendly questions, and guided learning tools.</td>
</tr>
<tr>
    <td>Project Impact</td>
    <td>The positive effect a project has on users, learning, or the community.</td>
    <td>Helps beginner students learn setup, file organization, SDLC, Scrum, and tool usage through a gamified classroom-style experience.</td>
</tr>
<tr>
    <td>Ethical Considerations</td>
    <td>Thinking about fairness, responsibility, safety, and possible consequences.</td>
    <td>The AI challenge prompts are designed to be beginner-friendly, avoid trick questions, use plain language, and give actionable feedback.</td>
</tr>
</table>

<h2>Other CS113 Terms Applicable to College Bound</h2>

<p>
The terms below apply to the broader College Bound project beyond the Mission Tools file.
Evidence comes from the College Bound repository, including its Jekyll site structure,
build setup, calendar feature, frontend API logic, and planned project infrastructure.
</p>

<table>
<tr>
<th>Term</th>
<th>Brief Description</th>
<th>How Used in College Bound</th>
</tr>

<tr>
<td>Stack/Queues</td>
<td>Structures that control the order data is added and removed.</td>
<td>Used in College Bound to organize student tasks, reminders, scholarship steps, and deadlines in the order they need to be completed.</td>
</tr>

<tr>
<td>Trees</td>
<td>Hierarchical structures where data branches from parent nodes to child nodes.</td>
<td>Used to organize college-planning resources in a parent-child structure, such as Academics → AP Classes → APUSH or Applications → Essays → Supplements.</td>
</tr>

<tr>
<td>Graphs</td>
<td>Structures made of nodes and connections used to represent relationships.</td>
<td>Used to represent relationships between colleges, majors, scholarships, deadlines, prerequisites, and preparation steps.</td>
</tr>

<tr>
<td>Hashing</td>
<td>A method of converting data into a fixed value for fast storage, lookup, or verification.</td>
<td>Used in the login system to securely verify user data, such as passwords or authentication tokens, without directly storing sensitive original values.</td>
</tr>

<tr>
<td>Deployment</td>
<td>The process of making a software project available for users.</td>
<td>Shown through the College Bound setup and deployment workflow, where the README explains installing Python/Ruby, running <code>./scripts/init.sh</code>, and using <code>make</code> to build or serve the site.</td>
</tr>

<tr>
<td>Docker</td>
<td>A tool that packages applications with their dependencies into containers.</td>
<td>Used to package the College Bound site and related services so the project can run consistently across different computers and deployment environments.</td>
</tr>

<tr>
<td>DNS Configuration</td>
<td>Setting up domain names so they point to the correct server or website.</td>
<td>Used to connect College Bound to a readable web address so users can access the site through a custom domain instead of only a default GitHub Pages URL.</td>
</tr>

<tr>
<td>nginx</td>
<td>A web server often used to serve websites or route requests to applications.</td>
<td>Used to route web traffic to the College Bound frontend and forward API requests to backend services when the project is deployed.</td>
</tr>

<tr>
<td>API Documentation</td>
<td>Information explaining how an API works and how to use its endpoints.</td>
<td>Supported by the frontend authentication logic, where the site sends a <code>fetch()</code> POST request to <code>/api/auth/exchange</code> to exchange an authorization code for login data.</td>
</tr>

<tr>
<td>Blog Portfolio</td>
<td>A collection of posts showing progress, learning, and completed work.</td>
<td>Used through the Jekyll blog/page structure, where pages use front matter such as <code>layout</code>, <code>title</code>, and <code>permalink</code>, and the post layout renders titles, dates, categories, and page content.</td>
</tr>
</table>