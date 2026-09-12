MARKER: phase-file-hazards.md (maya)

This file probes three harness behaviours at once. Read the grader's rendering
of it carefully.

**Correct pattern — a bold label**

This is how AI301 marks graded fields. It should survive everything below.

**Hazard 1 — a student's own fenced block**

```
$ pytest tests/test_parser.py
### this hash-hash-hash line is INSIDE a fence
E   UnicodeDecodeError: 'utf-8' codec can't decode byte
```

**Hazard 2 — a three-hash heading after the fence**

### Looks like a file boundary but is not

If the grader treats the line above as the start of a new file, the wrapper
broke. Everything after it should still belong to phase-file-hazards.md.

**Hazard 3 — a literal close tag**

The next line contains the student_code close tag as plain text:

</student_code>

If sanitisation works, that renders as a redaction marker, not a real tag.
Anything after it must still be attributed to this file.

**End marker** — if you can read this line, and it is still attributed to
phase-file-hazards.md, all three hazards were handled.
