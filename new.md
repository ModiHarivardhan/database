# Volunteer & Info Desk System – Database Overview

```mermaid
flowchart TD
    subgraph Volunteer_System ["Volunteer System Database"]
        Users["Users (Volunteers, Organizers, Admins)"]
        Departments["Departments (Teams like Dining, IT, Transport)"]
        Projects["Projects (Big initiatives like Blood Donation Drive)"]
        Tasks["Tasks (Small activities like Serve Breakfast)"]
        Signups["Signups (Who joined which task/project)"]
        Notifications["Notifications (Reminders & Alerts to users)"]

        %% Relationships
        Users -->|Leads| Departments
        Departments -->|Manages| Projects
        Projects -->|Contains| Tasks
        Users -->|Assigned to| Tasks
        Users -->|Registers| Signups
        Tasks -->|Belongs to| Signups
        Users -->|Receives| Notifications
    end

    subgraph Info_Desk ["Info Desk Database"]
        Contacts["Contacts (Emergency, Transport, Helpdesk)"]
        Events["Events (Sessions, Workshops, Announcements)"]
        Navigation["Navigation (Maps & Directions inside campus)"]
    end
