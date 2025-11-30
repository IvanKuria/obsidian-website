# Privacy Policy for About My Professor

*Last updated: November 30, 2025*

## What This Extension Does

About My Professor is a browser extension that displays Professor information from the campus directory page and Rate My Professors ratings directly on UCSC's MyUCSC enrollment pages to help students make informed course enrollment decisions.

## Information We Collect

**We collect NO personal information.** Specifically:

- ❌ No personal data is collected, stored, or transmitted to external servers
- ❌ No browsing history is tracked outside of UCSC enrollment pages
- ❌ No user accounts, login information, or authentication data
- ❌ No cookies are set or read by the extension
- ❌ No analytics, tracking, or usage telemetry

## Information We Access

The extension only accesses:

- **Public course information** already visible on MyUCSC enrollment pages (instructor names, course codes, sections)
- **Public professor ratings** from Rate My Professors website via their public GraphQL API
- This information is processed locally in your browser and is not sent to any servers controlled by this extension

## Local Data Storage

For performance optimization, the extension temporarily stores:

- **Cached professor ratings** in your browser's local storage for up to 30 days
- **Course-instructor mapping data** to avoid redundant API calls
- This data is stored locally on your device only and is automatically expired/refreshed
- No personal information is included in this cached data
- You can clear this cache at any time through browser storage management

## How It Works

1. **Detects** when you visit UCSC enrollment pages (MyUCSC or PISA)
2. **Extracts** instructor names from publicly visible course listings
3. **Queries** Rate My Professors' public API for matching professor ratings
4. **Displays** rating information inline within the existing page layout
5. **Caches** results temporarily to improve performance on subsequent visits

## Third-Party Services

The extension connects to:

- **Rate My Professors** - to fetch public professor ratings via their public GraphQL API
- **UCSC MyUCSC/PISA Systems** - to read publicly displayed course and instructor information
- No personal information is sent to any third-party service
- All API requests use publicly available endpoints that don't require authentication

## Data Sharing

- **No data is shared** with any third parties beyond the necessary API calls to Rate My Professors
- **No analytics** are collected or transmitted about your usage patterns
- **No tracking** occurs across different websites or browsing sessions
- The extension operates entirely within UCSC enrollment pages and Rate My Professors API

## Security

- All data processing occurs locally in your browser
- No server-side components or external databases are maintained by this extension
- The extension uses secure HTTPS connections for all API communications
- No sensitive information (passwords, personal details, etc.) is accessed or processed

## Changes to This Policy

- Any changes to this privacy policy will be reflected in updated versions of the extension
- Users will be notified of significant privacy-related changes through the Chrome Web Store
- The "Last updated" date at the top of this policy indicates when changes were made

## Your Rights

You can:
- **Disable the extension** at any time through Chrome's extension management
- **Clear cached data** by removing the extension or clearing browser storage
- **View stored data** using Chrome Developer Tools (Application > Storage > Local Storage)

## Contact & Support

- This extension is not affiliated with UC Santa Cruz or Rate My Professors
- For questions about this privacy policy or extension functionality, create an issue on the project's GitHub repository
- For broader privacy concerns, consult Chrome's extension privacy documentation

## Compliance

This extension:
- Adheres to Chrome Web Store privacy requirements
- Follows Google's extension privacy guidelines
- Implements data minimization principles (collecting only necessary information)
- Provides transparent disclosure of all data access and usage

---

**Privacy by Design**: This extension is built with privacy as a core principle - it simply enhances publicly available information without collecting, tracking, or storing any personal data about its users.