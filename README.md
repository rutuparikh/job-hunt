# Job Hunt

Job-search workflow repository for resume review, job matching, and application-specific resume optimization.

This repository currently documents the `resume-reviewer` skill.

## Repository Layout

```text
job-hunt/
|-- skills/
|   `-- resume-reviewer/
|       `-- SKILL.md
|-- applications/        # Private application workspaces; ignored by Git
|-- .gitignore
`-- README.md
```

## Privacy

The `applications/` directory is intentionally ignored by Git. Keep company-specific job descriptions, tailored resumes, PDFs, feedback files, and application notes there so they are not pushed to a remote repository.

## Resume Reviewer

`resume-reviewer` is a blunt hiring-manager style audit skill for Software Engineer resumes. It reviews a resume against a target job description and produces a single recommendations file with a harsh score, credibility issues, weak bullets, strongest technical signals, and rewrite guidance.

### Expected Inputs

For each review, prepare a folder containing:

```text
resume.pdf
job.txt
```

Rules:

- `resume.pdf` contains the candidate resume.
- `job.txt` contains the target job description.
- The job description file can have another name, but it should end in `.txt`.

### Expected Output

The skill creates one output file:

```text
hm-recommendations.txt
```

The first line of the output is always:

```text
Score: XX/100
```

### How To Use

1. Create or choose an application workspace under `applications/`.

   ```bash
   mkdir -p applications/company-role-name
   ```

2. Add the resume and job description.

   ```text
   applications/company-role-name/resume.pdf
   applications/company-role-name/job.txt
   ```

3. Ask Codex to run the `resume-reviewer` skill on that folder.

   Example prompt:

   ```text
   Use the resume-reviewer skill on applications/company-role-name.
   ```

4. Review the generated recommendations.

   ```text
   applications/company-role-name/hm-recommendations.txt
   ```

## Future Enhancements

This workflow will be enhanced over time with additional skills, including:

- Job fit evaluation
- ATS and technical recruiter screening
- Resume builder
