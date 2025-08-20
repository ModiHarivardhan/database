erDiagram
    USERS {
        string _id
        string name
        string gender
        string email
        string contact
        string whatsappNumber
        string address
        int age
        date DOB
        string country
        string state
        string city
        string currentLocation
        string abhyasiId
        string role
        string center
        string preferredCenter
        string preferredLanguage
        string preferredWorkType
        string profession
        string skills
        string interestedDepartments
        string account
        string availabilityStatus
        string location
        string timeZone
        date createdAt
        date updatedAt
    }

    DEPARTMENTS {
        string _id
        string name
        string description
        string category
        string departmentHeadId
        date createdAt
        date lastUpdated
    }

    TASKS {
        string _id
        string title
        string description
        string departmentId
        string type
        string status
        int totalSpots
        string location
        string requirements
        date startDate
        date endDate
        string startTime
        string endTime
        string poc
        string signups
        date createdAt
        string createdBy
        date updatedAt
    }

    PROJECTS {
        string _id
        string title
        string description
        string departmentId
        string approvalStatus
        string requiredSkills
        date createdAt
        string templateCreatedBy
        date templateCreatedAt
        date lastUpdated
    }

    PROJECT_APPLICATIONS {
        string volunteerName
        string contactNumber
        string email
        string whatsappNumber
        string volunteerId
        string abhyasiId
        string projectId
        date createdAt
        string status
        string attachments
    }

    SIGNUPS {
        string taskId
        string volunteerId
        string organizerId
        string status
        date createdAt
    }

    APP_NOTIFICATIONS {
        string _id
        string userId
        string message
        string type
        string status
        date createdAt
    }

    REGISTRATION_LOGS {
        string action
        string message
        string userId
        date createdAt
        string taskId
        string organizerId
    }

    ACTIVITY_LOGS {
        string activityType
        string message
        string userId
        date createdAt
        string details
    }

    %% Relationships
    USERS ||--o{ DEPARTMENTS : "heads"
    USERS ||--o{ TASKS : "creates"
    USERS ||--o{ SIGNUPS : "signs up"
    TASKS ||--o{ SIGNUPS : "has"
    DEPARTMENTS ||--o{ TASKS : "includes"
    PROJECTS ||--o{ PROJECT_APPLICATIONS : "has"
    USERS ||--o{ PROJECT_APPLICATIONS : "applies"
    USERS ||--o{ APP_NOTIFICATIONS : "receives"
    USERS ||--o{ REGISTRATION_LOGS : "creates"
    USERS ||--o{ ACTIVITY_LOGS : "creates"
