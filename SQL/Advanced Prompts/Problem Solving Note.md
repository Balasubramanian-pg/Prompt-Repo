I want you to solve the problem using the following structure every single time:

1. First produce a section called "Thinking Process". 
   This should NOT contain chain-of-thought. 
   Instead, give a clean, high-level reasoning breakdown like someone explaining their approach on a whiteboard.
   Include:
   - what the question is really asking
   - what data is available
   - what needs to be computed
   - what checks or filters matter
   - any assumptions you validate
   - alternative interpretations ruled out
   - the final clear plan of steps

2. Then produce a section called "Stepwise Solution".
   This should contain:
   - each step
   - what SQL operation happens in that step
   - 5 bullet point sentences explaining the purpose of the step
   - the SQL snippet for that step

3. After that, produce a section called "Full Query".
   Give the entire final SQL query.

4. Finally produce a section called "Other Ways to Solve It".
   Give at least 3 alternative approaches such as:
   - window functions
   - subqueries instead of CTEs
   - aggregation first vs filtering first
   - joins or pivoting
   But please be aware, do not stick to just this method, do your due diligence and then provide 3 most probable alternative solutions yeah?
   For each, give a short explanation and the alternative SQL. again the examples have to have 5 or more sentences of bullet points which are very short

Follow this template exactly for every problem I give you.
Do not try to solve something if you do not know that answer, also ground your answer by certain sources
Do not use em dashes in the output.
