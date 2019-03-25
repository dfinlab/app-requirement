## Deliverables:

1. App (Android & iOS)
2. Progressive web app(PWA) (webpage adaptable for phone and desktop)
3. Backend service (provides API for both App and PWA)

## Design

1. [App Design](https://invis.io/9ZR6XHQMJY2#/354242888_iPhone_XS_Copy_25)
2. [Web Design](https://projects.invisionapp.com/share/S5QVAH7FX23#/screens/353793544)

## Flows:

### User flow:

1. Ask for email -> 
2. Check the database if user existed, if yes, start to create profile (step 6), if not, continue ->
3. Send confirmation email ->
4. User confirms the email on email app ->
5. Ask for first name and last name ->
6. Ask for avatar ->
7. Ask for password ->
8. Start to import connections via Social accounts: Google, Facebook and LinkedIn, if they skip, switch to Phone contacts page (step 11) ->
9. If they choose any of these, ask for permission via OAuth and get their friends info ->
10. Store these information in the backend database and send out invitation emails via customer.io ->
11. Show “notify you once account is ready”, if they click “send invitation”, direct them to Import social connections page (step 9)
12. Import phone contacts from the phone, and let the user choose who to invite ->
13. Upload the chosen contacts to the server and send out invitation email/SMS via customer.io

### Friend Flow:

1. Got invitation email ->
2. Click the link in email ->
3. Land on User Flow step 1

## Backend API

### Get user profile
GET /api/user

### Login or Register

POST /api/user/login
request body ```json
{
  "email_phone":  "aaa@aaa.com",
  "password": "blabla",
  "create": false,
}```

### User edit
POST /api/user/edit

### User connections list
GET /api/user/connections

### Invite contacts

to be continued...
