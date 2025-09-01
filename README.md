# Axon History Tools

A collection of **Axon utility functions** for managing and testing history workflows in SkySpark.

---

## Features

This repo currently includes:

- **Backup tools** – export point history over a date span to Zinc files.  
- **Restore tools** – reload history from Zinc backups back into points.  
- **Helper functions** – match live points to the correct history columns in a backup file.  

---

## Design Principles

The functions are written with:

- Clear inline comments for maintainability.  
- Defensive guards (null handling, file existence checks).  
- Consistent reporting so results can be read at a glance.  

---

## Structure

/functions   – Axon functions (ready to paste into SkySpark)
/notes  – Annotated notes & explanations for each function

---

## Usage

1. **Backup** history for a date span into the project’s `io/` directory.  
2. Optionally **clear** history (`hisClear`) to test the restore process.  
3. **Restore** from the Zinc files to repopulate point histories.  

---

## Notes

- Functions assume connector tags such as `haystackCur` and `arcbeamCur`.  
- Backup files are written to the `io/` folder in Zinc format.  
- Restores automatically filter out null values, since SkySpark cannot write empty history rows.  
