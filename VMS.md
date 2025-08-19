flowchart LR
    subgraph VolunteerInfoCluster
        subgraph volunteer_system [Database: volunteer_system]
            users[users<br/>_id, name, email, phone, role, skills, availability]
            departments[departments<br/>_id, department_name, description, head_id]
            projects[projects<br/>_id, title, description, start_date, end_date, department_id]
            tasks[tasks<br/>_id, task_name, description, assigned_to, status, project_id]
            signups[signups<br/>_id, user_id, task_id/project_id, signup_date, status]
            notifications[notifications<br/>_id, user_id, message, type, read_status]

            %% Relationships
            users -->|head_id| departments
            departments -->|department_id| projects
            projects -->|project_id| tasks
            users -->|assigned_to| tasks
            users -->|user_id| signups
            tasks -->|task_id| signups
            users -->|user_id| notifications
        end

        subgraph info_desk [Database: info_desk]
            contacts[contacts<br/>_id, name, phone, email, query, status]
            events[events<br/>_id, title, description, date, time, location]
            navigation[navigation<br/>_id, place_name, description, map_coordinates]
        end
    end
