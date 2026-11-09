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


---

## 🗄️ Database Architecture (Cloud Firestore)

The project utilizes Google Cloud Firestore as its primary NoSQL document store. The core application schema for the **ASTRA Developers App** is structured into the following base collections within the default database instance (`(default)`):

| Collection | Description | Primary Fields |
| :--- | :--- | :--- |
| **`members`** | User profiles and account roles | `fullName`, `email`, `role` |
| **`events`** | Event metadata and reward point configurations | `title`, `location`, `pointsEarned` |
| **`partners`** | Participating organizations and sponsors | `name`, `category`, `isActive` |
| **`perks`** | Catalog of redeemable member rewards | `title`, `partnerId`, `stockQuantity` |
| **`vouchers`** | Generated reward claim tokens | `code`, `memberId`, `perkId`, `isRedeemed` |
| **`leaderboard`** | Aggregated member point standings | `memberId`, `fullName`, `currentPoints` |
| **`pointsLedger`** | Immutable point transaction audit log | `entryId`, `amount`, `type`, `referenceId` |
| **`attendances`** | Event check-in records | `attendanceId`, `eventId`, `memberId`, `pointsEarned` |
| **`digitalIds`** | Encrypted digital ID token hashes | `memberId`, `tokenHash`, `isRevoked` |

> **Operational Notes**:
> - **Isolated Legacy Data**: Existing production collections (`serviceRequests`, `counters`) serving the live ASTRAscend site are strictly segregated and maintained without modification.
> - **Dynamic Initialization**: Auxiliary/secondary schemas (e.g., `perkClaims`, `eventSecrets`, `uniqueStudentIds`, `uniqueEmails`) are managed dynamically at runtime by application services.
