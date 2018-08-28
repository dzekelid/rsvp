---
swagger: "2.0"
x-collection-name: Meetup
x-complete: 0
info:
  title: Meetup RSVP Create and Update
  description: Creates or updates an existing RSVP
  version: 1.0.0
host: api.meetup.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /rsvps:
    get:
      summary: Rsvps
      description: API method for accessing meetup rsvps
      operationId: deprecated
      x-api-path-slug: rsvps-get
      parameters:
      - in: query
        name: event_id
        description: Return members that RSVPd to events with these ID numbers [separated
          by commas]
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - RSVP
  /rsvp:
    post:
      summary: RSVP
      description: Creates a new Rsvp
      operationId: deprecated
      x-api-path-slug: rsvp-post
      parameters:
      - in: query
        name: answer_{qid}
        description: Answers to event survey questions
        type: string
      - in: query
        name: comments
        description: A comment to post along with the RSVP
        type: string
      - in: query
        name: event_id
        description: The event that you are RSVPing to
        type: string
      - in: query
        name: guests
        description: Number of guests also coming to the event
        type: string
      - in: query
        name: member_id
        description: Organizers and event hosts may RSVP on behalf of a member by
          specifying an ID here
        type: string
      - in: query
        name: rsvp
        description: The RSVP setting - value must be either yes
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - RSVP
  /:urlname/events/:event_id/rsvps/open:
    post:
      summary: Open Rsvps
      description: Opens rsvps for an event
      operationId: events
      x-api-path-slug: urlnameeventsevent-idrsvpsopen-post
      responses:
        200:
          description: OK
      tags:
      - Events
      - RSVP
  /:urlname/events/:event_id/rsvps/close:
    post:
      summary: Close Rsvps
      description: Closes rsvps for an event
      operationId: events
      x-api-path-slug: urlnameeventsevent-idrsvpsclose-post
      responses:
        200:
          description: OK
      tags:
      - Events
      - RSVP
  /:urlname/events/:event_id/rsvps:
    post:
      summary: RSVP Create and Update
      description: Creates or updates an existing RSVP
      operationId: rsvps
      x-api-path-slug: urlnameeventsevent-idrsvps-post
      parameters:
      - in: query
        name: agree_to_refund
        description: A boolean indicator used for Events with ticketing feeds to imply
          the Member has agreed to the Events refund policy
        type: string
      - in: query
        name: answer_{qid}
        description: Answers to Event survey questions
        type: string
      - in: query
        name: guests
        description: The number of guests Member will be attending with
        type: string
      - in: query
        name: opt_to_pay
        description: A boolean indicator used for Events with ticketing fees to imply
          the Member has opted to pay as part of the RSVP request
        type: string
      - in: query
        name: pro_email_share_optin
        description: The authenticated Members email opt in status
        type: string
      - in: query
        name: response
        description: The authenticated Members RSVP response
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - RSVP
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---