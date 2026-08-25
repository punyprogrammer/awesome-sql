# Question

<img width="1206" height="541" alt="image" src="https://github.com/user-attachments/assets/546efedd-047a-4463-aa64-4ae27d98442d" />

# Answer

```sql
-- Select the facility ID and the total number of slots booked
SELECT
    facid,

    -- Calculate the total slots booked for each facility
    SUM(book.slots) AS "Total Slots"

FROM cd.bookings AS book

-- Group bookings by facility
GROUP BY book.facid

-- Only include facilities with more than 1000 total slots
HAVING SUM(book.slots) > 1000

-- Sort the results by facility ID
ORDER BY facid;
```
