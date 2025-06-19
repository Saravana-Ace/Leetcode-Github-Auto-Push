# Leetcode-Github-Auto-Push

Automatically have your LeetCode submissions pushed to your GitHub repository. Keep the `Automated_Push` directory in your working git repository to automate your LeetCode submissions.

## Prerequisites

- Git repository already set up
- Docker installed on your system
- Active LeetCode account

## Setup Instructions

### 1. Retrieve Your LeetCode Session ID

> ⚠️ **IMPORTANT**: DO NOT SHARE YOUR LEETCODE SESSION ID WITH ANYONE

1. Sign into your LeetCode account in your browser
2. Open Developer Tools:
   - **Mac**: `Command + Option + I`
   - **Windows/Linux**: `F12` or `Ctrl + Shift + I`
3. Go to the **Network** tab
4. Filter by `graphql` to show only GraphQL requests
5. If you don't see anything just refresh your webpage to generate some requests
6. Click on any GraphQL request and go to **Headers**
7. Find **Request Headers** section and locate the `Cookie` header
8. Find `LEETCODE_SESSION=` in the cookie string and copy the value after it

### 2. Initial Setup

1. Clone this repository into your working git directory:
   ```bash
   git clone <repository-url>
   cd Automated_Push
   ```

2. Run the setup script to configure your credentials:
   ```bash
   python setup.py
   ```
   
3. Enter your LeetCode username and session ID when prompted

<!-- TODO -->
<!-- ### 3. Running with Docker -->

## How It Works

- The application checks for new LeetCode submissions every 30 seconds (can change this)
- When a new submission is detected, it automatically:
  - Downloads the submission code
  - Creates a Python file with the problem name
  - Commits the changes to your git repository
  - Pushes to your remote repository

<!-- ## Managing the Service

```bash
# View running containers
docker ps

# Stop the service
docker stop leetcode-bot

# Restart the service
docker restart leetcode-bot

# Remove the container
docker rm leetcode-bot
``` -->

<!-- ## Troubleshooting

- If the container stops unexpectedly, check logs with `docker logs leetcode-bot`
- Ensure your LeetCode session ID is valid (re-run setup.py if needed)
- Make sure your git repository has proper remote configuration -->