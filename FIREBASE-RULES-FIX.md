{
  "rules": {
    "users": {
      "$uid": {
        // ONLY the logged-in user can read/write their own data
        ".read": "auth != null && auth.uid === $uid",
        ".write": "auth != null && auth.uid === $uid"
      }
    },
    // Optional: Publicly readable data (adjust as needed)
    "publicData": {
      ".read": true,
      ".write": "auth != null"
    }
  }
}
