# Fighting the Knowledge Representation Bottleneck with Large Language Models (JURIX 2024)

This repository contains the support material for the paper *Fighting the Knowledge Representation Bottleneck with Large Language Models*.

- **[JURIX24_fighting_krb.ipynb](https://github.com/LegalMachineLab/JURIX24-fighting_krb/blob/main/JURIX24_fighting_krb.ipynb)**
  
  Jupyter Notebook with prompts, inputs, and outputs of experiments from the paper. Section *Legal Fragments* contains the original text of the articles, as well as the Prolog formalization by the legal KE.

- **[sentenza_4_3_eaw.txt](https://github.com/LegalMachineLab/JURIX24-fighting_krb/blob/main/sentenza_4_3_eaw.txt)**
  
  Full text of the judgment for case C-261/09.

- **[sentenza_4_6_eaw.txt](https://github.com/LegalMachineLab/JURIX24-fighting_krb/blob/main/sentenza_4_6_eaw.txt)**
  
  Full text of the judgment for case C-66/08.

### Task 1 - Article Generation

#### Prompt 1 - Complete from facts
<pre>
Given the following list of Prolog facts and rules:

List of Prolog Rules:

<b>...</b>

List of Prolog Facts:

<b>...</b>

Complete the representation of the following article:

<b>...</b>

Only use the Prolog facts provided.
New rules can be created, as long as they are based on existing facts.

The output should follow the following structure:

fragment of text 1
prolog representation 1

...

fragment of text n
prolog representation n

The goal of the rules is always the mandatory / optional refusal of the instrument.
Your output should contain only the required code inserted in a Markdown code block.
</pre>

#### Prompt 2 - Revise facts
<pre>
Given the following list of Prolog rules:

<b>...</b>

Identify possible problems:
- inconsistent naming or arity.
- fail to capture relevant information.
- no correspondance between natural language and rules.
- mixed legal conditions.

The output should include only the identified problems.

The output should follow the following structure:
problem 1
explanation of the problem
...
problem n
explanation of the problem

Your output should contain only the required code inserted in a Markdown code block.
</pre>


#### Prompt 3 - Apply Revision
<pre>
Given the following list of Prolog rules and a set of revisions:

List of Prolog Rules:

<b>...</b>

Revision:

<b>...</b>

Apply the revisions and solve the issues!

Your output should contain only the required code inserted in a Markdown code block.
</pre>

### Task 2 - Case Generation

#### Prompt 1 - Case law summary
<pre>
Provide a list of conditions related to the application of a ground of refusal according to European Law.
Here is the case law:

<b>...</b>

The output should be in the following format:
- Case Law Name
  - ground of refusal article
  - ground of refusal conditions
  - explanation of the elements
  - case law influences (Apply only the elements which add information to existing elements. Do not consider elements which expand the scope of the article for the legislator.)

</pre>

#### Prompt 2 - Case law rules
<pre>
Here are a list of elements that change the application of an article based on case law.
The list comes with an explanation for each element.

<b>...</b>

Your task is to create new rules which formalize the case law.
Use only the elements necessary for applying of the ground of refusal.
Follow this style:

<b>...</b>

This is the article which relates to the case:

<b>...</b>

Apply only the elements which add information to existing predicates.
Do not consider elements which expand the scope of the article for the legislator.

These rules shall contain only the relevant case law information.

The final output should be in the following format:
- Article applied
- New prolog rule
- Explanation of the conditions
</pre>
