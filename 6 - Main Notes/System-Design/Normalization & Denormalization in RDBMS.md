**Topic**: [[System Design]]

### 📌Normalization :-
- Breaking down *large tables* in to *smaller, related tables* and *establishing 
	relationships* between them.

- Minimizes **redundancy**, **simplicity**
- Don't do *over normalization*👎

- [[Employee Table Normalization Example]]
- Find the *department location* of ***emp_id: 2*** 🤔

```SQL
-- EID, EName, DepartmentLocation
-- Employee ka Department = Department ka Department

SELECT E.EmployeeID, E.EmployeeName, D.DepartmentLocation
FROM Employee E
JOIN Department D ON
E.Department = D.Department
WHERE E.EmployeeId = 2;
```

---
### 📌Denormalization :-
- **Deliberately** introducing **redundancy** into a *database table*.
- Opposite of *normalization*

🤔 [[But why normalizing and de-normalizing]]

→ [[System Design]]
