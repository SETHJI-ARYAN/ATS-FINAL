# ATS-FINAL# Pseudocode for Basic Applicant Tracking System (ATS)

# Define data structures
class JobPosting:
    attributes: title, description, requirements, application_deadline

class Candidate:
    attributes: name, email, resume, applied_jobs

class ATS:
    attributes: job_postings, candidates

    method create_job_posting(title, description, requirements, application_deadline):
        # Create a new job posting
        job = new JobPosting(title, description, requirements, application_deadline)
        job_postings.add(job)
        return job

    method submit_resume(candidate, job, resume):
        # Candidate submits a resume for a specific job
        candidate.resume = resume
        candidate.applied_jobs.add(job)

    method filter_candidates(job, skill_requirements):
        # Filter candidates based on job's skill requirements
        qualified_candidates = []
        for candidate in candidates:
            if candidate in job.applied_candidates and candidate.skills >= skill_requirements:
                qualified_candidates.add(candidate)
        return qualified_candidates

# Example Usage
ats = new ATS()
job1 = ats.create_job_posting("Software Developer", "Develop software applications", "Programming skills", "2023-12-31")

# Candidate applies for a job
applicant1 = new Candidate("John Doe", "john@example.com")
ats.submit_resume(applicant1, job1, "Resume content, skills, etc.")

# Filter candidates for a job based on skill requirements
qualified_candidates = ats.filter_candidates(job1, "Strong programming skills")

# Display qualified candidates
for candidate in qualified_candidates:
    print(candidate.name, candidate.email)
