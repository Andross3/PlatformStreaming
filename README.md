erDiagram
    genres ||--o{ videos : "categorizes"
    users ||--o{ subscriptions : "purchases"
    users ||--o{ watch_history : "watches"
    videos ||--o{ watch_history : "logged in"

    genres {
        int id PK
        varchar genre_name
        text genre_description
    }

    videos {
        int id PK
        int genre_id FK
        varchar movie_title
        text movie_description
        date released_date
        decimal rating
        int total_duration_min
    }

    users {
        int id PK
        varchar username
        varchar email
        varchar mobile
    }

    subscriptions {
        int id PK
        int user_id FK
        varchar subscription_type
        decimal amount_paid
    }

    watch_history {
        int id PK
        int user_id FK
        int video_id FK
        int watch_min
    }
