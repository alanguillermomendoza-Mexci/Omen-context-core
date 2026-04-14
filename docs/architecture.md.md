

**Architecture Overview**



Omen Context Core is designed as a local-first contextual memory system for AI-assisted technical workflows.



Its current architecture is centered around a SQLite database that stores project knowledge in a structured way instead of relying on unstable conversation memory. The system is intentionally offline, modular and prepared for future local expansion.



**Current Core Components**



\- SQLite database as persistent local memory

\- SQL schema for reproducible database creation

\- Python initialization script for local setup

\- Public documentation describing structure and purpose



**Structural Model**



The database is organized around a central contextual entries table supported by relational tables for:



\- projects

\- modules

\- entry types

\- priorities

\- statuses

\- tags

\- entry-tag mappings

\- entry relations

\- activity log



This structure allows the system to preserve continuity, trace decisions and recover project state with more reliability than chat memory alone.



**Design Priorities**



\- preserve context

\- remain fully local

\- avoid cloud dependency

\- support future local AI integration

\- stay modular and expandable

\- protect sensitive working data by keeping the real database outside version control



**Repository Boundary**



This repository contains the public structure of the system only. The actual working database and private contextual entries remain local and are excluded from the repository by design.



Nada más.

