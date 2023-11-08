# Post Mortem: M-Banking Web Application Failure - August 11, 2023

## Issue Summary

- **Duration:** The outage occurred on Friday, August 11, 2023, from 09:00 AM to 01:00 PM (UTC +3).
- **Impact:** The main branch code push error resulted in the unavailability of critical banking services, affecting approximately 30% of our users. Users experienced service disruptions, failed transactions, and an inability to access their accounts.
- **Root Cause:** The root cause was the accidental code push to the main branch instead of a test branch, leading to a structural change in the application's file system and service interruptions.

## Timeline

- **Issue Detection:** The issue was detected at 09:00 AM (UTC) when monitoring alerts indicated a sudden surge in error rates and a spike in customer complaints.
- **Actions Taken:** Our engineering team immediately started investigating the problem, assuming it was a database issue due to the initial symptoms. However, further investigation revealed that the issue was related to the codebase.
- **Misleading Paths:** Initially, there was a focus on database-related debugging, which consumed approximately one hour before realizing that the issue was with the codebase. The code push error was not immediately apparent.
- **Escalation:** After identifying the issue's nature, the incident was escalated to the development and DevOps teams for a coordinated effort to rectify the codebase problem.
- **Resolution:** The issue was resolved by rolling back the erroneous code push and restoring the application to its previous working state. This process took approximately three hours.

## Root Cause and Resolution

- **Root Cause:** The root cause of the outage was the accidental code push to the main branch. This code change resulted in a substantial modification of the application's file structure, leading to the disruption of critical services.
- **Resolution:** To fix the issue, the following steps were taken:
  1. The erroneous code push was identified and rolled back.
  2. The code repository was restored to the previous stable version.
  3. All services were verified and tested to ensure they were functioning as expected.
  4. The application was brought back online incrementally to avoid further disruptions.

## Corrective and Preventative Measures

- **Improvements/Fixes:**
  - Implement stricter access controls for the code repository, allowing only authorized users to push to the main branch.
  - Enhance the code review process with additional checks to prevent unintentional code deployments to the main branch.
  - Expand automated testing and continuous integration to validate code structure and service functionality after each deployment.
  - Provide comprehensive documentation and training to reinforce development processes and prevent future incidents.
  - Improve the incident response plan for faster detection, isolation, and resolution of issues.

- **Specific Tasks:**
  - Restrict main branch access to specific users with proper permissions.
  - Enhance code review processes to catch code changes directed to the wrong branches.
  - Implement additional automated tests for code structure and service functionality.
  - Conduct mandatory training sessions for developers on branch management.
  - Revise and strengthen the incident response plan, emphasizing quicker detection and resolution.

In conclusion, the outage on August 11, 2023, stemmed from an accidental code push to the main branch and resulted in service disruptions for a significant portion of our users. We have taken immediate corrective actions and outlined comprehensive preventative measures to prevent similar incidents in the future and maintain the reliability of our banking web application. We appreciate our customers' patience during this disruption and are committed to providing secure and uninterrupted banking services.

<img href="https://i.chzbgr.com/full/9340630528/hFC589711/spotify-playlist-songs-about-git" alt="git these issues">