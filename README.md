# C8 AI Challenge

An insurance company needs to estimate the cost of vehicle damage. 
The insurer submits an image of the damaged vehicle, and the system initially qualifies the severity of the damage.

Some key that the system have to answer:
* What type of vehicle is it? (Car, Boat, or another category?)
* Is the damage minor (e.g., a small dent) or severe?

# Step-by-Step Guide

## Set Up a Camunda 8 SaaS Environment


Create or use an existing Camunda 8 SaaS account. 

## Build the Process

During this step, we will use AI Copilot to build the process incrementally.

Initial Process Creation:

Ask AI Copilot to generate a process using the following description:

```
A user submits a document. The first step calls an AI service to analyze the document, identifying the vehicle type and estimating the damage cost. If the estimated cost is below $5,000, the application is automatically accepted, and reimbursement proceeds. If the cost exceeds this threshold, the case is assigned to a manual review task, where an operator can accept or reject the application."
```

Refining the Process by adding a Decision Logic:

```shell
Before manual validation, introduce a decision gateway that directs cases to different manual review tasks based on the vehicle type (Car, Boat, or Truck).
```

Add a new step
```
Coverage Verification:

Add a service task that checks if the user’s insurance policy covers the identified vehicle type. Keep this task manual for now.
```
### Build the Submission Form

A form is required for users to submit damage reports. The AI Copilot can assist in creating this form.

AI Copilot Request:
```
In the form, users must upload an image labeled as 'damageImg', which will be stored as a document. The contract number, available in the URL parameter 'contractMo', should be displayed as a read-only text field."
```

## Build the Validation Form

This form will be used during the manual review step.

AI Copilot Request:
```
In the validation form, display the stored document ('damageImg'). Also, show 'vehicleType' and 'estimateCost' as read-only fields. Include two buttons: 'Accepted' and 'Rejected', which update the process variable 'status'."
```
Additional Requirement:
```
Add a text field named 'comments' where the user can leave remarks. Save this as a document named 'comments'. (Verification needed if this is feasible.)"
```

## Create an Account on Mistral


To be coordinated with William.

## Integrate Mistral AI with the Process


To be coordinated with William.

## Deploy the Process

Once the process is finalized, deploy it in the Camunda 8 SaaS environment.

# Test the Implementation

Provide a collection of test images to verify the workflow and AI functionality.

# Conclusion

By following these steps, you will successfully implement an AI-powered claims processing system in Camunda 8.
