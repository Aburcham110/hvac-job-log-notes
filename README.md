# HVAC/R Job-Log Notes (Educational)

Python **stdlib-only** CLI for structured service-call notes and **EPA 608–style** technician-file / customer-copy fields.

> **NOT legal advice. NOT a compliance system.** Educational record-keeping aid only. Use your employer’s official forms and follow current EPA / local requirements.

## Fields

- Customer / site, equipment, model / serial
- Refrigerant type, lbs added / recovered, system charge, recovery equipment ID, vacuum
- Leak found / repaired (Y/N) + notes
- Work performed, parts used, follow-ups
- Cert type noted, customer copy / tech file flags

Every export prints a hard disclaimer.

## Requirements

- Python 3.9+

## Quick start

```bash
cd hvac-job-log-notes
python3 job_log.py --help
python3 job_log.py -i
```

### Flags → plain text on stdout

```bash
python3 job_log.py \
  --technician "A. Tech" \
  --customer "Example Cafe" \
  --site "123 Main St" \
  --equipment "3-ton RTU" \
  --model "XYZ-36" \
  --serial "SN123" \
  --refrigerant R-410A \
  --lbs-added 2.0 \
  --lbs-recovered 0 \
  --leak-found N \
  --leak-repaired N \
  --work "Replaced contactor; verified charge" \
  --parts "Contactor 40A" \
  --follow-ups "None" \
  --format text
```

### Markdown file export

```bash
python3 job_log.py -i --format markdown -o job-summary.md
```

### JSON input

```bash
python3 job_log.py --json-in sample.json --format markdown -o out.md
```
