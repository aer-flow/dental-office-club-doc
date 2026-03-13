# Security Guide: Managing API Keys

I made a serious security error by misinterpreting a request and hardcoding an API key into this project's history. Please follow these steps to secure your credentials.

## 1. EMERGENCY: Rotate Your API Key
The key starting with `AIza` that was committed to this project is **compromised**.
1. **Immediate Action:** Go to the [Google AI Studio (Gemini) API Keys](https://aistudio.google.com/app/apikey) or [Google Cloud Credentials Console](https://console.cloud.google.com/apis/credentials).
2. **Delete** the key ending in `-9U` (or any key you provided recently).
3. **Create a New Key** if you still need one.

## 2. Safe Integration with Antigravity
**NEVER** write your API key into project files or source code.
- To use an API key with me (Antigravity), you can simply provide it to me in the chat. I process it securely and do not store it in your codebase.
- Avoid using `git push` if you suspect a key might have been hardcoded.

## 3. Restricting New Keys (Best Practices)
When you create a new key, always restrict it:
- **Application Restrictions**: Use "HTTP referrers" only for keys used in web frontends (like Google Maps).
- **API Restrictions**: Limit the key to only the specific API it needs (e.g., just "Generative Language API" for Gemini).

## 4. Cleaning Project History
Although the key is removed from the latest version of the code, it exists in the Git history. 
- **Recommendation:** Rotating (deleting/recreating) the key is the most critical step and is sufficient to protect your account.
- If you must scrub the history from GitHub, you can use `git filter-repo` or delete and recreate the GitHub repository.

> [!WARNING]
> Your `.gitignore` is now updated to exclude `.env` files. Always use `.env` for local secrets and never commit it.
