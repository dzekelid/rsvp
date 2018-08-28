---
swagger: "2.0"
x-collection-name: Meetup
x-complete: 0
info:
  title: Meetup Rsvps
  description: API method for accessing meetup rsvps
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