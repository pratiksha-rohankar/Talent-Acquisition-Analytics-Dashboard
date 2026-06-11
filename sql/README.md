SELECT * FROM candidates;

-- Total Applicants
SELECT COUNT(*) FROM candidates;

-- Selected Candidates
SELECT COUNT(*)
FROM candidates
WHERE FinalStatus = 'Selected';

-- Selection Rate
SELECT
COUNT(*) * 100.0 / (SELECT COUNT(*) FROM candidates)
FROM candidates
WHERE FinalStatus = 'Selected';

-- Drop-off per Stage
SELECT DropStage, COUNT(*) AS total
FROM candidates
WHERE DropStage != 'None'
GROUP BY DropStage
ORDER BY total DESC;

-- Recruitment Strategy
SELECT RecruitmentStrategy, COUNT(*) AS total
FROM candidates
GROUP BY RecruitmentStrategy;

-- Selected by Strategy
SELECT RecruitmentStrategy, COUNT(*) AS selected
FROM candidates
WHERE FinalStatus = 'Selected'
GROUP BY RecruitmentStrategy;

-- High Performers vs Selection
SELECT 
CASE 
WHEN ResumeScore >= 70 AND TechnicalScore >= 70 THEN 'High Performer'
ELSE 'Others'
END AS category,
COUNT(*) AS total,
SUM(CASE WHEN FinalStatus='Selected' THEN 1 ELSE 0 END) AS selected
FROM candidates
GROUP BY category;

-- Distance Impact on Hiring
SELECT 
CASE 
WHEN DistanceFromCompany < 10 THEN 'Near'
WHEN DistanceFromCompany BETWEEN 10 AND 30 THEN 'Medium'
ELSE 'Far'
END AS distance_group,
COUNT(*) AS total,
SUM(CASE WHEN FinalStatus='Selected' THEN 1 ELSE 0 END) AS selected,
ROUND(
SUM(CASE WHEN FinalStatus='Selected' THEN 1 ELSE 0 END) * 100.0 / COUNT(*),2
) AS selection_rate
FROM candidates
GROUP BY distance_group;

-- Personality Score Impact
SELECT 
CASE 
WHEN PersonalityScore >= 70 THEN 'High'
WHEN PersonalityScore >= 50 THEN 'Medium'
ELSE 'Low'
END AS personality_level,
COUNT(*) AS total,
SUM(CASE WHEN FinalStatus='Selected' THEN 1 ELSE 0 END) AS selected
FROM candidates
GROUP BY personality_level;

-- Interview Score vs Selection
SELECT 
CASE 
WHEN PersonalityScore >= 70 THEN 'High'
WHEN PersonalityScore >= 50 THEN 'Medium'
ELSE 'Low'
END AS personality_level,
COUNT(*) AS total,
SUM(CASE WHEN FinalStatus='Selected' THEN 1 ELSE 0 END) AS selected,
ROUND(
SUM(CASE WHEN FinalStatus='Selected' THEN 1 ELSE 0 END) * 100.0 / COUNT(*),2
) AS selection_rate
FROM candidates
GROUP BY personality_level;

-- Rejection Reason Analysis
SELECT DropReason, COUNT(*) AS total
FROM candidates
WHERE DropReason != 'N/A'
GROUP BY DropReason
ORDER BY total DESC;
