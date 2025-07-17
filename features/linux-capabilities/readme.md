# Linux capabilities
## What are Linux capabilities
They are a set of flags that manage the permissions of a program running in priviledge mode. 
In a traditional, all-powerful superuser privileges into distinct units of authority.
Instead of granting full root access, the kernel allows processes to hold just the specific capabilities they need to perform their tasks.

This model limits the harm of priviledge escalation exploits, as they won't have unrestricted system access.

> **Note:** You can learn more about linux capabilities in [the official man-pages regarding this topic](https://man7.org/linux/man-pages/man7/capabilities.7.html). It's honestly an interesting topic I recommend reading, even if it just is a quick look.