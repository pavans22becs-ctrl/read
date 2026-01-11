graph TD
    A[User Opens App] --> B[Grant Camera/Media Permissions]
    B --> C[Permissions Granted?]
    C -->|Yes| D[Display Camera View with AR Overlay]
    C -->|No| E[Show Error: Permissions Required]
    E --> F[Retry Permissions]

    D --> G[Capture Image/Video or Pick from Gallery]
    G --> H[Preview Captured Media]
    H --> I[Confirm and Send to Server]

    I --> J[Server Receives Request]
    J --> K[Validate and Process]
    K --> L[Object Detection with YOLO]
    L --> M[OCR with EasyOCR]
    M --> N[Background Removal with rembg]
    N --> O[3D Reconstruction with COLMAP/ffmpeg]
    O --> P[Generate GLB Model]

    P --> Q[Return Results to App]
    Q --> R[Display Results: Objects, Text, Images, 3D Model]

    R --> S[User Interactions]
    S --> T[Select Object for Extraction]
    T --> U[Send Extract Request]
    U --> V[Server Processes Extraction]
    V --> W[Return Cropped PNG]
    W --> R

    S --> X[Edit Extracted Text]
    X --> Y[Update Display]

    S --> Z[Initiate 3D Scan]
    Z --> AA[Upload Video]
    AA --> O

    S --> BB[Send to Clipboard]
    BB --> CC[Send to Clipboard Server]
    CC --> DD[Push to PC Clipboard]

    R --> EE[End/Repeat Process]
    F --> D
    DD --> EE
    Y --> EE
