# MongoDB
MongoDB Assessment
## Installation Instruction
### Requirements
<br>- Python 3.10 or above
<br>- MongoDB Community Server
<br>- Jupyter Notebook or VS Code
<br>- Git
### Clone the Repository
```bash
git clone <this-repository-link>
cd <repository-folder>
```
### Prepare the CSV Files
<br>Place the starter CSV files in the project folder
<br>
### Justify your design choices in a README, referencing best-practice and research.
<br>I noticed that all three collections have an attendee_id column when I designed the schema. In traditional databases, this universal and unique column is often used as a bridge for joins. Therefore, I chose attendee_id as the core of the optimized schema and based on this, established the attendees set.
<br>I embedded the feedback and ticket.scans collections into the new collection because they usually have small amounts of data. Even if an attendee repeatedly enters, they will not have too many tickets, and feedback usually corresponds to the number of times they attend, so it also will not be too many. Differently, one attendance may have lots of  movements, so RFID collection is not suitable for embedding into the attended set due to its movement column. Therefore, I utilized the uniqueness of RFID_tag as a foreign key for the reference and connected the attended collection.
### Why Choose Index:
<br>Indexing is an effective performance optimisation technique because it reduces the amount of data that must be examined during query execution. Without indexes, MongoDB often performs collection scans, which require higher computation and lead to slower performance.
<br>Indexes improve efficiency by narrowing the search space, especially when query selectivity is high. Cardinality is also important. Fields with many distinct values usually provide better index performance because they help identify fewer matching records. 
<br>However, indexes are not free. They consume additional memory and storage, and they increase update and insert overhead. Therefore, indexes should be created mainly for fields that are queried frequently and have meaningful filtering value.
