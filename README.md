# Voice Authentication System

This Python script implements a basic voice authentication system using audio recordings. It allows users to register their voice and later authenticate themselves by comparing their recorded voice with the registered one.

## Requirements

To run this script, you need to have the following Python libraries installed:

- `numpy`
- `scipy`
- `pyaudio`
- `scikit-learn`


You can install these libraries using pip:

```
pip install numpy scipy pyaudio scikit-learn 
```

## How to Use

1. **Recording Audio**: 
    - Run the script and enter your user ID when prompted.
    - Follow the instructions to record your voice. The script will save the recorded audio in a directory named `USER_VOICE_DIR` with the file name as your user ID.

2. **Authentication**:
    - After registering your voice, you can authenticate yourself by running the script again.
    - Press Enter to start the authentication process.
    - Follow the instructions to record your voice again.
    - The script will compare the recorded audio with the previously registered voice.
    - If the similarity between the voices is above a certain threshold (`threshold`), authentication is successful; otherwise, it fails.

## Code Explanation

- `record_audio(file_path, duration=3, rate=8000, chunk=1024)`: Function to record audio using the microphone and save it to the specified file path.
- `compare_audio(audio1, audio2)`: Function to compare two audio files using Euclidean distance and Dynamic Time Warping (DTW).
- `authenticate_user(user_id, new_audio_path)`: Function to authenticate a user by comparing the recorded voice with the registered voice.
- `main()`: Main function to handle user interactions, such as registering voice and authenticating users.

## Important Notes

- Ensure that the `USER_VOICE_DIR` directory exists before running the script. This directory is used to store registered user voices.
- Adjust the `threshold` value according to your requirement for voice similarity. The default value is set to `125000`.
- The script currently supports only mono-channel (single-channel) audio files in WAV format.

