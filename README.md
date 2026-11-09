# DEMO-test

---

## 🗄️ Database Schema (Cloud Firestore)

Primary base collections initialized in Cloud Firestore (`(default)`):

- **`members`**: User profiles (`fullName`, `email`, `role`)
- **`events`**: Event management (`title`, `location`, `pointsEarned`)
- **`partners`**: Organization/Sponsor partners (`name`, `category`, `isActive`)
- **`perks`**: Member perks/rewards (`title`, `partnerId`, `stockQuantity`)
- **`vouchers`**: Claimed/Generated vouchers (`code`, `memberId`, `perkId`, `isRedeemed`)
- **`leaderboard`**: Member points standings (`memberId`, `fullName`, `currentPoints`)
- **`pointsLedger`**: Points transaction log (`entryId`, `amount`, `type`, `referenceId`)
- **`attendances`**: Event check-ins (`attendanceId`, `eventId`, `memberId`, `pointsEarned`)
- **`digitalIds`**: Digital ID tokens (`memberId`, `tokenHash`, `isRevoked`)

*Note: Existing Astrascend live collections (`serviceRequests`, `counters`) remain untouched. Secondary helper collections (`perkClaims`, `eventSecrets`, etc.) are dynamically populated by backend application code.*
