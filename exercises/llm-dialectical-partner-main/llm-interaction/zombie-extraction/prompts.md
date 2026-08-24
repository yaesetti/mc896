# Prompts

## Round 1

I want to develop a Python code to extract data in a structured format from clinical reports of a fictitious scenario of zombies. The first three attachments are examples of these clinical reports in Markdown. The applications of this structured format will be:
* Find records containing specific symptoms/diseases
* Associate symptoms with diseases (diagnostic support)
* Analyze symptoms common/specific to diseases

In this first step, I want to discuss the format of the structured format with you. I have the following ideas:
1) CSV format - easy to process, less flexible
2) JSON format - mostly good for process, more flexible
3) both formats - a bit harder to implement

What are your ideas about that? Do not present the schemas for now; I want to restrict the discussion to the approach.

## Round 2

Let us follow the both-formats approach. I would like to design a solution in Python classes; my idea is to organize it in classes/interfaces following a Builder design pattern, as follows:
1) Extract class with the methods:
   1.1) parse - receives a name of a file and an output format, parses this file, and produces the output;
  1.2) parse_set - receives a directory and calls parse for each file;
2) Builder interface with methods:
  2.0) start - start building
  2.1) record - new patient record (all the following methods address this record)
  2.2) patient_id - the patient ID
  2.3) name - the patient name
  2.4) symptom - an observed symptom for the patient
  2.5) diagnosis - the patient diagnosis
  2.6) blood analysis
  2.7) previous diagnosis
  2.8) finish - finish building
3) Two classes that implement the Builder interface:
  3.1) CSV Builder - produces a CSV
  3.2) JSON Builder - produces a JSON
I would like you to check the consistency and name selection of the proposed classes/interfaces/methods.

## Round 3

I agree with all of your suggestions. Could you please produce two files for me:
1) a Mermaid file with the UML diagram of classes
2) a markdown file documenting the architecture
