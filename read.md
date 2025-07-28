flowchart TD

%% === Client Side ===
subgraph User_Device[User Device (Flutter App)]
    A1[Camera + Image Upload]
    A2[Local Notifications]
    A3[Gamification Engine]
    A4[User App (Flutter UI)]
end

%% === Authentication ===
A4 --> Auth[Firebase Auth / Auth0]

%% === Connections to Backend ===
A4 --> B1[Backend API (NestJS)]

%% === Backend Core ===
subgraph Backend_System[Backend Infrastructure]
    B1 --> AI[Skin AI API (SageMaker / VisualDx)]
    B1 --> Weather[Weather API (OpenWeather / Tomorrow.io)]
    B1 --> Affiliate[Affiliate API (Amazon, Skimlinks)]
    B1 --> DB[(PostgreSQL Database)]
    B1 --> S3[S3 Image Storage]
    B1 --> Notify[Push Notifications (FCM)]
    B1 --> Analytics[Analytics (Mixpanel / Firebase)]
end

%% === Other Data Flows ===
A1 --> B1
A2 --> Notify
A3 --> B1
