# Launch EC2 Instance Using AI

This repository contains a project that combines AI-driven hand gesture recognition with AWS EC2 instance management. The system allows you to launch EC2 instances by recognizing specific hand gestures using a webcam feed.

## Features

1. **Real-Time Hand Gesture Recognition**
   - Uses the webcam feed to recognize hand gestures.
   - Recognizes gestures like "index finger up" to trigger actions.

2. **AWS EC2 Instance Management**
   - Launches an EC2 instance programmatically upon detecting specific gestures.

3. **Mobile-Friendly Interface**
   - A responsive HTML interface to stream webcam feed and send it to the backend.

4. **Custom Video Controls**
   - Includes features like play/pause, seek, fullscreen toggle, and more for video playback.

## File Structure

### HTML and Frontend
- **`mobile.html`**
  - The main frontend interface for the application.
  - Features a video container to stream webcam feed and controls for playback.

- **`mobile-web-video-playback.css`**
  - Stylesheet for the video playback and user interface.

- **`tiny-fullscreen-shim.js`**
  - Handles fullscreen compatibility for various browsers and devices.

- **`mobile-web-video-playback.js`**
  - Provides custom video controls, background playback, and fullscreen handling.

### Backend
- **`upload.py`**
  - Python CGI script that handles image uploads from the frontend.
  - Recognizes hand gestures using the `cvzone.HandTrackingModule` library.
  - Interacts with AWS EC2 to launch instances based on detected gestures.

## Setup Instructions

### Prerequisites
1. Python 3.x installed on your server.
2. AWS SDK for Python (Boto3) installed.
3. AWS credentials with EC2 permissions.
4. A webcam-enabled device for testing.
5. Required Python libraries:
   - `cvzone`
   - `opencv-python`
   - `boto3`

### Steps
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/launch-ec2-ai.git
   ```

2. Set up a web server (e.g., Apache) to serve the `mobile.html` file.

3. Place the `upload.py` script in the server's CGI directory.

4. Update the `aws_access_key_id` and `aws_secret_access_key` in `upload.py` with your AWS credentials.

5. Create the directory `myupload/` on your server to store uploaded images.

6. Open the `mobile.html` file in a browser to start the application.

## How It Works

1. The webcam feed is streamed via the browser.
2. Every 2 seconds, a snapshot of the feed is sent to the backend (`upload.py`) as an image.
3. The backend uses `cvzone.HandTrackingModule` to detect hand gestures in the uploaded image.
4. If a specific gesture (e.g., "index finger up") is detected, an EC2 instance is launched.

## Hand Gestures Supported
- **Index Finger Up**: Launches an EC2 instance.
- **Index and Middle Finger Up**: Future actions can be configured.

## Troubleshooting

1. **Webcam Access Issues**:
   - Ensure your browser has permission to access the webcam.

2. **AWS Connection Errors**:
   - Verify your AWS credentials and permissions.

3. **Hand Gesture Not Recognized**:
   - Check the lighting and positioning of your hand.

## Future Enhancements
- Add more hand gestures for additional AWS actions.
- Integrate with other cloud providers like Azure or Google Cloud.
- Enhance the frontend UI for better usability.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---

### Author
Ayush

If you have any questions or suggestions, feel free to reach out!

