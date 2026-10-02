# Privacy Policy — OOD Sync

**Effective date:** October 2, 2026
**Application:** OOD Sync (Google Cloud project `ood-ai`)
**Operator:** OOD Studio — contact: santz.1996@gmail.com

OOD Sync is an internal automation that moves design briefs and their media between a client agency's project boards and OOD Studio's task board, and copies reference files between two Google Drive accounts that belong to the operator. It is not a public service: the only users are the operator and the designer who works with the operator.

## 1. What the application does with Google

The application connects to Google Drive on two accounts, each authorized separately through Google's OAuth consent flow:

| Account | Scope requested | What the app does with it |
|---|---|---|
| Agency account (read-only) | `https://www.googleapis.com/auth/drive.readonly` | Reads the metadata (name, size, MD5 checksum) of folders and files that a brief links to, and downloads those files so they can be copied to the studio account. It never creates, modifies, shares or deletes anything on this account. |
| Studio account (read/write) | `https://www.googleapis.com/auth/drive` | Looks for the studio's own copies of those files under the folder `01-OOD`, creates subfolders there when a copy is missing, and uploads the copied files. It never touches files outside `01-OOD` and never changes sharing settings. |

The application does not use Gmail, Calendar, Contacts, Photos or any other Google service.

## 2. Data we access and store

- **File metadata and file contents** from the folders linked in a brief. File contents are downloaded to a temporary folder on the operator's computer only for the time it takes to upload them to the studio account, then deleted.
- **A cached index** of folder and file names, sizes and checksums for the studio account, kept for up to 24 hours on the operator's computer to avoid repeated listings.
- **OAuth tokens** (access and refresh tokens) for each account, stored as files on the operator's computer. They are never transmitted anywhere except to Google's own token endpoint.
- **Links** to the resulting studio-account folders, which are posted as comments on the studio's task board so the designer can find the files.

We do not collect analytics, personal profile information, contacts or any data unrelated to the linked files. The only identity information read is the account email, used to confirm which account a token belongs to.

## 3. How data is used and shared

Data is used solely to copy design reference files from the agency account to the studio account and to tell the designer where they are. It is not sold, rented or shared with third parties, and it is not used for advertising, profiling or training machine-learning models.

The only parties that see Google Drive links produced by the app are the operator and the studio's designer, through the studio's task board.

## 4. Data retention

- Downloaded file contents: deleted right after upload, and in any case within 14 days by the app's clean-up routine.
- Cached indexes and temporary files: deleted within 14 days.
- Copies in the studio account: kept as part of the studio's normal project files, under the studio's control.
- OAuth tokens: kept until revoked (see section 6).

## 5. Security

Tokens and credentials are stored only on the operator's computer, outside version control, and are readable only by the operator's user account. All communication with Google uses HTTPS. The read-only scope on the agency account guarantees the app cannot alter the agency's data.

## 6. Your choices and revocation

Either account can revoke the application's access at any time at https://myaccount.google.com/permissions. Revoking access immediately stops the app from reading or writing that account; locally stored tokens become invalid and can be deleted. Files already copied to the studio account remain there under the studio's control and can be deleted by the studio at any time.

## 7. Google API Services User Data Policy

OOD Sync's use and transfer of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements.

## 8. Changes and contact

If this policy changes, the updated version will be published at the same location with a new effective date. Questions: santz.1996@gmail.com.
