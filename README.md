# Password Reset Part 1 - Send Mail 🚀

A UiPath automation project that handles the first part of the password reset process by sending notification emails to password reset operators.

## Description

This automation workflow receives employee details and sends an email notification to the password reset operator. It is part of a larger password reset process.

## Features

- Validates input parameters (employee code, email, and secret code)
- Reads mail template from storage bucket
- Sends formatted email notification to password reset operator
- Handles errors and provides status feedback

## Prerequisites

- UiPath Studio 25.0.167.0 or later
- Required NuGet packages:
  - UiPath.Mail.Activities (2.4.10)
  - UiPath.System.Activities (25.4.4)

## Input Arguments

| Argument | Type | Required | Description |
|----------|------|----------|-------------|
| istrOrchestrator | String | Yes | Orchestrator path (default: "Advance Projects/Password Reset") |
| istrEmpSecrateCode | String | Yes | Employee secret code |
| istrEmpCode | String | Yes | Employee code |
| istrEmpEmail | String | Yes | Employee email address |

## Output Arguments

| Argument | Type | Description |
|----------|------|-------------|
| ostrStatus | String | Process execution status ("Success" or error message) |

## Workflow Structure

1. **Main.xaml**
   - Main workflow orchestrating the process
   - Validates input parameters
   - Handles exceptions

2. **10.a InitAllSettings.xaml**
   - Initializes settings and reads mail template

3. **10.b Process.xaml**
   - Handles email preparation and sending

## Error Handling

- Input validation for required parameters
- Try-catch blocks for exception handling
- Error logging
- Status reporting through ostrStatus

## Storage Requirements

- Requires access to storage bucket containing email template
- Template path: "P1 Mail Template.txt"

## Project Settings

- Execution Type: Workflow
- Output Type: Process
- Framework: Windows
