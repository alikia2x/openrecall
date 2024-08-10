# OpenRewind

OpenRewind is an open-source alternative to [rewind.ai](https://rewind.ai), forked from [OpenRecall](https://github.com/openrecall/openrecall).

As this project is still in its early stages, you might not see significant progress just yet.

## To-dos

### Update the OCR Engine

OpenRecall currently uses docTR as its OCR engine, but it performs inadequately. On my MacBook Air M2 (2022), processing a screenshot takes around 20 seconds, with CPU usage peaking at over 400%. During this time, screenshots cannot be captured, and the engine appears to recognize only Latin characters.

To address this, we plan to replace the OCR engine with a more efficient alternative that supports multiple writing systems. We are considering [Tesseract](https://github.com/tesseract-ocr/tesseract), which supports multiple languages and is faster, though it still falls short of our desired results. (As reference, rewind.ai runs on same machine with avearge CPU usage of 40%)

### Implement a Task Queue/Scheduler

Currently, OpenRecall's OCR recognition and database operations are synchronous (blocking). This results in increased screenshot frequency, as described in the previous section.

Our next goal is to introduce a task queue to handle high-load tasks (such as OCR, indexing, and archiving) asynchronously. This will ensure that time-sensitive tasks (like capturing screenshots) are prioritized.

### Improve the Frontend

The current frontend of OpenRecall is quite basic. Given my expertise in web development, I will build a more robust frontend from scratch, using Python solely as a daemon/backend server.

We are also considering using Electron to deliver a near-native experience, aiming to match the functionality of [rewind.ai](https://rewind.ai).

### Add More Features

We will be implementing the [feature list](https://github.com/openrecall/openrecall/discussions/9) proposed in the OpenRecall repository. Stay tuned for updates.

### THE FURTHER FUTURE: Deployment & Refactoring

We are exploring ways to simplify the download, installation, and usage of this Python-based program, especially as we introduce new technologies (such as web dev / Electron).

Initially, we are considering Docker as a deployment solution. [Docker Desktop](https://www.docker.com/products/docker-desktop/) is available for macOS and Windows users and offers a more user-friendly experience compared to command-line Python installations and dependency management.

However, Docker is a temporary solution. In the future, we plan to transition OpenRewind to the [Electron](https://www.electronjs.org/) technology stack and gradually migrate Python components to Node.js.
