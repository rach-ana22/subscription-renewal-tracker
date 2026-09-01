# subscription-renewal-tracker

An n8n automation that monitors subscription renewal emails, stores it in Google Sheets, and automatically sends reminders through mail and creates Google Calendar events.

## Problem

Subscription renewal emails can easily be missed, especially when multiple services renew at different times.

This workflow automates the tracking and reminder process.

## What it does

1. Runs on a scheduled trigger
2. Retrieves emails from Gmail
3. Detects the subscription/service
4. Extracts:
   - Service
   - Amount
   - Currency
   - Renewal date
   - User email
5. Stores the subscription data in Google Sheets
6. Calculates days until renewal
7. Routes subscriptions based on renewal timing
8. Sends Gmail reminders
9. Creates Google Calendar events

## Workflow

1. Schedule Trigger
2. Gmail - Get Many Messages
3. Python - Extract Subscription Data
4. Google Sheets
5. JavaScript - Calculate Renewal Status
6. Google Sheets
7. Switch: 0 days → Gmail reminder, 3 days → Google Calendar event

## Technologies

- n8n
- Gmail
- Google Sheets
- Google Calendar
- Python
- JavaScript

## Example

A renewal email containing:

Service: Netflix
Amount: ₹299
Renewal date: September 4, 2026

is converted into structured data and stored in Google Sheets.

The workflow then determines that the renewal is 3 days away and creates the appropriate reminder/calendar action.

## Results

The workflow was tested with multiple renewal emails.

- Renewal information extracted successfully
- Data stored in Google Sheets
- 0-day renewal routed correctly
- 3-day renewal routed correctly
- Gmail reminder successfully sent
- Google Calendar event successfully created

## Workflow File

The exported n8n workflow is available here

## Setup

1. Import the JSON workflow into n8n
2. Configure Gmail OAuth credentials
3. Configure Google Sheets credentials
4. Configure Google Calendar credentials
5. Replace the example spreadsheet/calendar values
6. Activate the workflow
