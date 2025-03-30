# RabbetSystemDesign

## Background

As part of a lender’s workflow, they receive 100s of pages of documentation that must be related back to a budget and to each other. Without Rabbet, this is a very manual process – people print out or notate PDFs, cross-referencing the budget and a checklist. This happens every month, for every construction loan. To speed up the process and reduce human error, we want to allow the user to upload these files and build a representation of the project to run automated checks.

## Prompt

Your goal is to design a proof-of-concept application that allows the user to upload files and store structured information about those files. Because of the quantity of files uploaded, we want the system to be able to determine the type of file within the domain (invoice, receipt, etc.) and extract structured information. No automated system is perfect, though, so we also need to allow the user to correct information.

At a basic level, the minimum requirements are:

1. Accepts files and persists the file data (assume S3, GCS, or similar)
2. System determines the domain type of file (think “invoice”, not “pdf”)
3. System extracts structured information from the file
4. The user can interact with the file to correct any data the system got wrong or missed (including the type itself)

Our product wants to support at least the following file types (though there could be more to follow):

* Budget: a list of line items, the amount budgeted, and the amount that has been requested so far (always an Excel document/xlsx)
* Change order: a request to change the budget (always a PDF)
* Invoice: a request for payment from a vendor (always a PDF)
* Pay application: similar to an invoice but specific for construction costs (always a PDF)

### Non-Requirements

* Determining exactly how type determination or data extraction works. Having a general starting point or some options/considerations here is sufficient.
* Any rules or validation that take into consideration the entire state of the project. Our goal is to get to where we can run those checks – we don’t need to determine how at this point.

### Tips

* We’re looking for how you would solve the problem. Some people like to spend some time ahead of the call going through some options on their own; others would like to wait until the call so they can ask clarifying questions before jumping into the design. Neither approach is inherently better! We neither reward nor punish people based on how much they’ve solved the problem before the call.
* Please come prepared with some way of documenting your proposed design. This can be a diagraming tool like draw.io, a google doc, spreadsheet, or even just a txt file in your text editor.
* We generally want to see at least a high-level layout of the data architecture, how data flows through the system, and any key actions/steps. However you’d like to structure that is up to you, though if you’d like a starting point, you’re welcome to use our tech plan template.
* There are no meta tests. So long as you’re prepped with a way to document your design and have read this prompt, you should be fine. There are no extra points for using our tech plan template, pre-solving the problem, etc. This info is simply supplied ahead of time in the hopes that it will be helpful.
* We are more focused on the backend architecture, but feel free to include any user flows/frontend considerations as it impacts the backend design.
* PDFs can contain text or images of text.
* Ask clarifying questions!

## Tech plan

### Diagram

```mermaid
```