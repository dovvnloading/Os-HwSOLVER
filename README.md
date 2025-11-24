
<div align="center">

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=googlebard&logoColor=white)

# Os-HwSOLVER

A premium, claymorphic AI tutor and homework assistant powered by Google's Gemini 3.0 and 2.5 multimodal models.

[View Demo / Report Bug](https://github.com/dovvnloading/Os-HwSOLVER/issues)

<br />


<img src="https://github.com/user-attachments/assets/f8e6121a-128f-4023-9aec-c797be01a98a" width="250" />
<img src="https://github.com/user-attachments/assets/d8e884b0-1332-4e4e-87a8-e573aea1d357" width="250" />
<img src="https://github.com/user-attachments/assets/01ff21b8-8e16-4dfb-b300-a17137cd9d0c" width="250" />

</div>

## Overview

Os-HwSOLVER is a next-generation educational tool designed to bridge the gap between static homework help and interactive tutoring. Built with React 19 and the Google GenAI SDK, it leverages the latest advancements in multimodal AI to perceive, reason, and converse.

The application features a distinct "Claymorphic" (Soft UI) design system, providing a tactile, engaging user experience that reduces cognitive load during study sessions.

## Key Features

### 1. Visual Problem Solver
*   **Multimodal Analysis:** Users can upload images of handwritten or printed homework.
*   **Deep Reasoning:** Utilizes `gemini-3-pro-preview` for complex step-by-step mathematical and scientific reasoning.
*   **Markdown Rendering:** Solutions are formatted with LaTeX-style precision, supporting code blocks, equations, and structured lists.
*   **Text-to-Speech:** Integrated TTS allows the AI to read the solution aloud for auditory learning.

### 2. Live Tutor Mode
*   **Real-time Interaction:** Features a low-latency voice interface using the Gemini Multimodal Live API via WebSockets.
*   **Bi-directional Audio:** Users can speak naturally to the AI, which processes audio inputs (PCM 16kHz) and responds with human-like voice output (PCM 24kHz).
*   **Interruptibility:** The system supports natural conversation flow.

### 3. Adaptive Intelligence
*   **Model Selection:** Users can toggle between models based on their needs:
    *   **Gemini 3.0 Pro:** Highest reasoning capability for complex logic.
    *   **Gemini 2.5 Flash:** Balanced speed and intelligence for general queries.
    *   **Gemini 2.5 Flash-Lite:** Optimized for rapid definitions and simple questions.
*   **Thinking Budgets:** Configured to utilize extended thinking tokens for harder problems.

## Technology Stack

*   **Frontend Framework:** React 19
*   **Build Tool:** Vite
*   **Language:** TypeScript (Strict mode)
*   **Styling:** Tailwind CSS (Custom configuration for Claymorphism/Neumorphism shadows)
*   **AI Integration:** `@google/genai` SDK
*   **Audio Processing:** Web Audio API (ScriptProcessorNode for PCM stream handling)
*   **Icons:** Lucide React

## Getting Started

Follow these instructions to set up the project locally.

### Prerequisites

*   Node.js (v18 or higher)
*   npm or yarn
*   A Google Gemini API Key

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/dovvnloading/Os-HwSOLVER.git
    cd Os-HwSOLVER
    ```

2.  Install dependencies:
    ```bash
    npm install
    ```

3.  Environment Configuration:
    Create a `.env.local` file in the root directory and add your API key:
    ```env
    GEMINI_API_KEY=your_actual_api_key_here
    ```

4.  Start the development server:
    ```bash
    npm run dev
    ```

5.  Open your browser and navigate to `http://localhost:3000`.

## Architecture Notes

### Audio Handling
The application implements a custom audio pipeline to handle the Gemini Live API requirements.
*   **Input:** Microphone input is downsampled to 16kHz PCM mono before being sent via WebSocket.
*   **Output:** Received audio chunks (base64) are decoded into an AudioBuffer and played via a gapless queueing system to ensure smooth voice playback.

### Model Configuration
The application is pre-configured to use specific model snapshots for stability.
*   Solver: Defaults to `gemini-3-pro-preview`.
*   Tutor: Defaults to `gemini-2.5-flash-native-audio-preview`.

## Credits

**Matthew Wesney**
<br />
Lead Developer & UX Lead

## License

Distributed under the Apache 2.0 License. See `LICENSE` for more information.
