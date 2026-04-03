━━━━━━━━━━━━━━━━━━━━━━━━━━
MANDATORY GLOBAL RULES
━━━━━━━━━━━━━━━━━━━━━━━━━━

Output strictly valid JSON.
Do NOT return markdown.
Do NOT return explanations.
Do NOT include text outside JSON.
All fields are mandatory.
Do not return null values.
Escape all internal quotes using backslash.
Ensure JSON is parsable using JSON.parse().
Base ALL output strictly on the provided document.
If a feature is not explicitly mentioned or logically implied, DO NOT generate test cases for it.
Do NOT assume post-process workflows (e.g., dashboard, logout, reports, APIs) unless explicitly described.
Do NOT introduce infrastructure, DevOps, or deployment cases unless the document defines them as requirements.
If ambiguity exists, generate clearly labeled QA assumptions inside the assumptions section only.

━━━━━━━━━━━━━━━━━━━━━━━━━━
FULL DOCUMENT COVERAGE RULES
━━━━━━━━━━━━━━━━━━━━━━━━━━

You MUST:

Identify and extract ALL requirement statements from the document.
Classify each into:
Functional
Non-Functional
Security
Performance
Usability
Compatibility
Integration
Data Validation
Compliance (if applicable)
Constraint
Assumption
Generate at least:
1 Positive test case per functional requirement
1 Negative test case per functional requirement
1 Edge or Boundary test case where applicable
1 Non-functional validation case per NFR
1 Security validation case per security-related requirement
Performance test case if performance criteria exist
Compatibility test case if platform/browser/device mentioned
Compliance validation if regulatory constraints exist
If document includes internal logic, calculations, workflows, or validation rules:
Generate white-box test considerations
Include boundary value analysis
Include equivalence partitioning
Include decision condition coverage
Ensure zero requirement remains untested.

━━━━━━━━━━━━━━━━━━━━━━━━━━
STRICT SCOPE CONTROL
━━━━━━━━━━━━━━━━━━━━━━━━━━

Do NOT extrapolate beyond document scope.
Do NOT create imaginary modules.
Do NOT assume architecture unless described.
Do NOT create logout/session/dashboard unless explicitly written.
Do NOT generate deployment tests unless explicitly required.
System Requirements section must only influence environment assumptions, not create standalone infrastructure tests unless required.

━━━━━━━━━━━━━━━━━━━━━━━━━━
RISK & PRIORITY RULES
━━━━━━━━━━━━━━━━━━━━━━━━━━

Determine risk level based on:

Domain criticality (Healthcare/Banking/Aviation → High)
Data sensitivity
Regulatory impact
User impact

Map severity & priority logically:

Business critical failure → Critical / Highest
Major functionality failure → High / High
Partial degradation → Medium / Medium
Cosmetic issue → Low / Low

━━━━━━━━━━━━━━━━━━━━━━━━━━
INPUT DOCUMENT
━━━━━━━━━━━━━━━━━━━━━━━━━━

{{ $json["text"] }}

━━━━━━━━━━━━━━━━━━━━━━━━━━
OUTPUT FORMAT
━━━━━━━━━━━━━━━━━━━━━━━━━━

{
"document_title": "Derived from document",
"detected_domain": "Auto-detected from context",
"system_type": "Web/Mobile/API/Desktop/Embedded/Other",
"overall_risk_level": "High/Medium/Low",
"coverage_summary": {
"total_requirements_identified": "number",
"functional_count": "number",
"non_functional_count": "number",
"security_count": "number",
"performance_count": "number",
"usability_count": "number",
"compatibility_count": "number",
"integration_count": "number",
"compliance_count": "number"
},
"assumptions": ["string"],
"requirement_traceability_matrix": [
{
"requirement_id": "Derived or extracted ID",
"requirement_type": "Functional/Non-Functional/etc",
"mapped_test_case_ids": ["TC-001", "TC-002"]
}
],
"test_cases": [
{
"test_case_id": "TC-001",
"requirement_reference": "Exact requirement text or ID",
"test_category": "Functional/BlackBox/WhiteBox/Security/etc",
"scenario_type": "Positive/Negative/Edge/Boundary",
"test_case_title": "Enterprise-level title",
"test_objective": "Validation purpose",
"preconditions": ["Precondition"],
"test_steps": ["Step 1", "Step 2"],
"test_data": "Structured realistic data",
"expected_result": "Measurable deterministic result",
"priority": "Highest/High/Medium/Low/Lowest",
"severity": "Critical/High/Medium/Low",
"automation_candidate": "Yes/No"
}
]
}

Return ONLY valid raw JSON.

━━━━━━━━━━━━━━━━━━━━━━━━━━
END OF INSTRUCTIONS
━━━━━━━━━━━━━━━━━━━━━━━━━━
