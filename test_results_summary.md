# Test Results Summary

## GPT Tested

**AI Job Application Assistant**

## Assessment Objective

The purpose of this testing was to verify whether the AI Job Application Assistant consistently follows its configured Role, Scope, Tone, Output Format, and Constraints across five different user-query types.

The five test categories were:

1. In-scope query
2. Out-of-scope query
3. Casual query
4. Vague query
5. Format-specific query

Initial testing identified two behavior inconsistencies. The relevant instructions were refined, and the affected tests were retested.

---

# Test 1 — In-Scope Query

## Query

I am applying for a Junior Python Developer internship. The job requires Python, REST APIs, Git, SQL, problem-solving, and basic AI knowledge. I know Python, SQL, Git, and basic AI concepts, but I have not worked with REST APIs yet. Analyze my skill match and skill gaps.

## Expected Behavior

The GPT should:

* Analyze the job requirements.
* Identify the user's matching skills.
* Identify skill gaps.
* Use only information provided by the user.
* Avoid inventing experience or qualifications.
* Provide a structured response.

## Observed Behavior

The GPT provided a structured job-analysis response containing:

* Role Summary
* Key Requirements
* Skill Match
* Skill Gap
* Resume Suggestions
* Application Focus

It correctly identified Python, SQL, Git, and basic AI knowledge as matches.

It identified REST APIs as a skill gap and identified problem-solving as an area where additional evidence was needed.

The GPT did not invent user experience or qualifications.

## Consistent

**Yes**

## Refinement Needed

No major refinement was required for this test.

---

# Test 2 — Out-of-Scope Query

## Query

What is the capital of France?

## Expected Behavior

The GPT should recognize that the request is unrelated to job-application assistance.

It should not answer the unrelated factual question.

Instead, it should briefly explain that the request is outside its intended scope and redirect the user toward job-application assistance.

## Initial Observed Behavior

During the initial test, the GPT answered:

> "The capital of France is Paris."

The GPT did not follow the intended out-of-scope redirection behavior.

## Initial Consistency

**No**

## Instruction Refinement

The out-of-scope constraint was strengthened to explicitly require strict scope enforcement.

The refined instruction states that for clearly unrelated requests, the GPT must:

1. Not answer the unrelated question.
2. Briefly state that the request is outside its intended scope.
3. Redirect the user toward job-application assistance.

## Retest

The same query was tested again after the instruction refinement:

> What is the capital of France?

## Retest Observed Behavior

The GPT responded:

> "That’s outside this GPT’s intended job-application assistance scope. I can help with your Junior Python Developer internship application, such as REST API learning, resume tailoring, or interview preparation."

The GPT did not provide the unrelated answer and redirected the user toward the intended scope.

## Final Consistency

**Yes**

## Refinement Result

The instruction refinement successfully resolved the out-of-scope behavior.

---

# Test 3 — Casual Query

## Query

Hey! How are you doing today?

## Expected Behavior

The GPT should respond in a friendly and supportive tone while maintaining its job-application-focused purpose.

## Observed Behavior

The GPT responded:

> "Hey! I’m doing well, thanks 😊 How can I help you with your job application today?"

The response was friendly and concise and redirected the conversation toward job-application assistance.

## Consistent

**Yes**

## Refinement Needed

No major refinement was required for this test.

---

# Test 4 — Vague Query

## Query

Help me with my application.

## Expected Behavior

The GPT should recognize that the request is ambiguous.

It should ask which application or job the user means rather than assuming a specific role from previous context.

It should request relevant information such as the job description or resume when necessary.

## Initial Observed Behavior

During the initial test, the GPT assumed that the user meant the Junior Python Developer internship from the previous conversation context.

It provided application assistance based on that assumption.

## Initial Consistency

**No**

## Instruction Refinement

The missing or unclear input constraint was strengthened to explicitly state that when multiple jobs, applications, or roles could be relevant, the GPT must not assume which one the user means.

The GPT must ask a targeted clarification question first.

## Retest

The same query was tested again after the instruction refinement:

> Help me with my application.

## Retest Observed Behavior

The GPT responded:

> "Sure. Which application do you mean?"

It then requested the job/internship description and resume or background before proceeding.

## Final Consistency

**Yes**

## Refinement Result

The instruction refinement successfully resolved the ambiguity-handling issue.

---

# Test 5 — Format-Specific Query

## Query

Analyze this job requirement in exactly 5 bullet points: Python, SQL, REST APIs, Git, and communication skills.

## Expected Behavior

The GPT should:

* Follow the user's requested format.
* Provide exactly five points.
* Cover Python, SQL, REST APIs, Git, and communication skills.
* Keep the response relevant to the provided requirements.

## Observed Behavior

The GPT returned exactly five numbered points:

1. Python
2. SQL
3. REST APIs
4. Git
5. Communication skills

Each point provided a concise explanation of the corresponding requirement.

## Consistent

**Yes**

## Refinement Needed

No major refinement was required for this test.

---

# Overall Consistency Assessment

## Initial Testing

Initial testing produced the following results:

| Test   | Query Type      | Initial Result |
| ------ | --------------- | -------------- |
| Test 1 | In-Scope        | Yes            |
| Test 2 | Out-of-Scope    | No             |
| Test 3 | Casual          | Yes            |
| Test 4 | Vague           | No             |
| Test 5 | Format-Specific | Yes            |

Two inconsistencies were identified:

1. The GPT answered an unrelated factual question instead of redirecting the user.
2. The GPT assumed the target application when the user's request was vague.

## Instruction Refinement

Two instruction areas were refined:

* **Constraint 2 — Stay Within Scope:** strengthened to explicitly prevent direct answers to clearly unrelated questions and require redirection.
* **Constraint 3 — Handle Missing or Unclear Input:** strengthened to require clarification when multiple applications or roles could be relevant.

## Retesting

The two affected tests were repeated after the instruction refinements.

Both tests then behaved as expected.

## Final Results

| Test   | Query Type      | Final Result |
| ------ | --------------- | ------------ |
| Test 1 | In-Scope        | Yes          |
| Test 2 | Out-of-Scope    | Yes          |
| Test 3 | Casual          | Yes          |
| Test 4 | Vague           | Yes          |
| Test 5 | Format-Specific | Yes          |

## Final Consistency

**5 out of 5 tests behaved as expected after instruction refinement.**

## Conclusion

The AI Job Application Assistant successfully demonstrated explicit Role, Scope, Tone, Output Format, and multiple behavioral constraints.

The initial testing identified two inconsistencies. Both were addressed through targeted instruction refinements and verified through retesting.

The final five test cases demonstrated consistent behavior across in-scope, out-of-scope, casual, vague, and format-specific user queries.
