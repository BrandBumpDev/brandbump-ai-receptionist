# BrandBump AI Receptionist Architecture

Caller
→ BrandBump Verizon number
→ Verizon call forwarding
→ Twilio voice number
→ Twilio voice webhook
→ CES Twilio Adapter on Cloud Run
→ Firestore deployment lookup
→ Google CX Agent Studio deployment

## Google Cloud

Project: brandbump
Region: us-east1

## Cloud Run

Service: ces-twilio-adapter

## Firestore

Collection: ces-twilio-adapter-mappings

The document ID is the Twilio number in E.164 format.

The document contains a string field named:

deployment_id

## Security

The Twilio Auth Token is stored in Google Secret Manager.

The repository must never contain:

- Twilio Auth Token
- Gmail app passwords
- OAuth tokens
- Service-account private keys
- Environment files containing credentials
