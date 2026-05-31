# Timesheets Template

A practical timesheets tracker that displays time entries from Google Sheets and lets team members submit new work logs through SheetBest. It includes status filters, billable tracking, approval state, summary metrics, and realistic sample data.

## Features

- Timesheet table with employee, client, project, date, task, hours, and notes
- Search and filters for status and billable work
- Summary metrics for total hours, billable hours, submitted entries, and approved entries
- Time entry form with generated entry IDs and submission timestamps
- Live SheetBest API endpoint plus JSON, CSV, and public Google Sheet sample data
- Responsive design powered by Tailwind CSS

## Quick Start

1. Clone the template repository:
   ```bash
   git clone https://github.com/sheetbest/timesheets-template.git
   cd timesheets-template
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start a local server:
   ```bash
   npm run dev
   ```

4. Open the template in your browser and review the sample entries.

## Sheet Format

Create a Google Sheet tab named `Timesheets` with these columns:

| EntryId | Employee | Client | Project | Date | Start | End | Hours | Task | Notes | Billable | Status | ApprovedBy | SubmittedAt |
|---------|----------|--------|---------|------|-------|-----|-------|------|-------|----------|--------|------------|-------------|
| Text | Text | Text | Text | Date | Time | Time | Number | Text | Text | Yes/No | Text | Text | DateTime |

## Sample Data

This template includes:

- `timesheets.json` for local read-only preview data
- `timesheets.csv` for importing the same rows into Google Sheets
- [Public sample Google Sheet](https://docs.google.com/spreadsheets/d/1F-GV1V86RTXXdJw9_UMTEShxWiUAcybPdRoLHZd7MdA/edit) with the same schema and demo rows
- Live SheetBest endpoint: `https://api.sheetbest.com/sheets/1f5b6dbe-51eb-41e0-a452-85e4d3ba3c8f/tabs/Timesheets`

To use your own copy:

1. Make a copy of the public sample Google Sheet, or import `timesheets.csv` into your own Google Sheet.
2. Confirm the sheet has a tab named `Timesheets`.
3. Connect the sheet in SheetBest.
4. Replace the read and write endpoints in `index.html`.

## API Configuration

### Read Data

The template is wired to a live SheetBest demo endpoint:

```html
<tbody data-sheet-best="https://api.sheetbest.com/sheets/1f5b6dbe-51eb-41e0-a452-85e4d3ba3c8f/tabs/Timesheets">
```

To use local static preview data instead, replace it with:

```html
<tbody data-sheet-best="./timesheets.json">
```

To use your own SheetBest connection, replace it with your endpoint:

```html
<tbody data-sheet-best="https://api.sheetbest.com/sheets/YOUR_SHEET_ID/tabs/Timesheets">
```

### Write Data

The form is wired to the same live demo endpoint:

```html
<form data-sheet-best="https://api.sheetbest.com/sheets/1f5b6dbe-51eb-41e0-a452-85e4d3ba3c8f/tabs/Timesheets">
```

To use your own sheet, replace the form endpoint:

```html
<form data-sheet-best="https://api.sheetbest.com/sheets/YOUR_SHEET_ID/tabs/Timesheets">
```

with your connected SheetBest endpoint.

## Status Values

The template styles these status values by default:

- `Submitted`
- `In Review`
- `Approved`
- `Needs Changes`

You can add more statuses by updating the status filter options and the `decorateRows()` function in `index.html`.

## Use Cases

- Agency client timesheets
- Consultant work logs
- Project billing reports
- Internal approval queues
- Lightweight freelancer time tracking

## Documentation

- [SheetBest API Documentation](https://docs.sheetbest.com)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

## License

MIT License - feel free to use in your projects.
