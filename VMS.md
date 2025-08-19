# Volunteer & Info Desk System – Database Overview

```mermaid
flowchart TD
    subgraph Volunteer_System [Volunteer System Database]
        Users[Users 👥\n(Volunteers, Organizers, Admins)]
        Departments[Departments 🏢\n(Teams like Dining, IT, Transport)]
        Projects[Projects 📂\n(Big initiatives like "Blood Donation Drive")]
        Tasks[Tasks ✅\n(Small activities like "Serve Breakfast")]
        Signups[Signups 📝\n(Who joined which task/project)]
        Notifications[Notifications 🔔\n(Reminders & Alerts to users)]

        %% Relationships
        Users -->|Leads| Departments
        Departments -->|Manages| Projects
        Projects -->|Contains| Tasks
        Users -->|Assigned to| Tasks
        Users -->|Registers| Signups
        Tasks -->|Belongs to| Signups
        Users -->|Receives| Notifications
    end

    subgraph Info_Desk [Info Desk Database]
        Contacts[Contacts ☎️\n(Emergency, Transport, Helpdesk)]
        Events[Events 📅\n(Sessions, Workshops, Announcements)]
        Navigation[Navigation 🗺️\n(Maps & Directions inside campus)]
    end
