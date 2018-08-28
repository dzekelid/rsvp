---
swagger: "2.0"
x-collection-name: Meetup
x-complete: 0
info:
  title: Meetup OpenEvents
  description: Searches for recent and upcoming public events hosted by Meetup groups.
    Its search window  is the past one month through the next three months, and is
    subject to change. Open Events is optimized to search for current events by location,
    category, topic, or text, and only lists Meetups that have **3 or more RSVPs**.
    The number or results returned with each request is not guaranteed to be the same
    as the page size due to secondary filtering. If you're looking for a particular
    event or events within a particular group, use the standard [Events](/meetup_api/docs/2/events/)
    method.
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
    get:
      summary: Event RSVP list
      description: Retrieves list of event RSVPs
      operationId: rsvps
      x-api-path-slug: urlnameeventsevent-idrsvps-get
      parameters:
      - in: query
        name: desc
        description: Boolean value controling sort order of results
        type: string
      - in: query
        name: fields
        description: A comma-delimited list of optional fields to append to the response
        type: string
      - in: query
        name: order
        description: The sort order of returned RSVPs
        type: string
      - in: query
        name: response
        description: Filter returned list to one or more of the following RSVP responses
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - RSVP
  /2/open_events:
    get:
      summary: OpenEvents
      description: Searches for recent and upcoming public events hosted by Meetup
        groups. Its search window  is the past one month through the next three months,
        and is subject to change. Open Events is optimized to search for current events
        by location, category, topic, or text, and only lists Meetups that have **3
        or more RSVPs**. The number or results returned with each request is not guaranteed
        to be the same as the page size due to secondary filtering. If you're looking
        for a particular event or events within a particular group, use the standard
        [Events](/meetup_api/docs/2/events/) method.
      operationId: events
      x-api-path-slug: 2open-events-get
      parameters:
      - in: query
        name: and_text
        description: Changes the interpretation of the text field from ORd terms to
          ANDd terms
        type: string
      - in: query
        name: api_version
        description: "2"
        type: string
      - in: query
        name: category
        description: Return events in the specified category or categories specified
          by commas
        type: string
      - in: query
        name: city
        description: A valid city
        type: string
      - in: query
        name: country
        description: A valid country code
        type: string
      - in: query
        name: fields
        description: Request that additional fields (separated by commas) be included
          in the output
        type: string
      - in: query
        name: lat
        description: A valid latitude, limits the returned group events to those within
          radius miles
        type: string
      - in: query
        name: limited_events
        description: Include limited event information for private groups that wish
          to expose only a small amount of information about their events
        type: string
      - in: query
        name: lon
        description: A valid longitude, limits the returned group events to those
          within radius miles
        type: string
      - in: query
        name: radius
        description: Radius, in miles for geographic requests, default 25
        type: string
      - in: query
        name: since_count
        description: Request that some number of recent messages be sent immediately,
          if available
        type: string
      - in: query
        name: since_mtime
        description: Return events with an mtime greater than the supplied time, in
          milliseconds since the epoch
        type: string
      - in: query
        name: state
        description: If searching in a country with states, a valid 2 character state
          code
        type: string
      - in: query
        name: status
        description: Status may be upcoming, past or both separated by a comma
        type: string
      - in: query
        name: text
        description: Events that contain the given term or terms somewhere in their
          content
        type: string
      - in: query
        name: text_format
        description: Format of the description text, html or plain
        type: string
      - in: query
        name: time
        description: Return events scheduled within the given time range, defined
          by two times separated with a single comma
        type: string
      - in: query
        name: topic
        description: Return events in the specified topic or topics specified by commas
        type: string
      - in: query
        name: zip
        description: A valid US zip code, limits the returned groups to those within
          radius miles
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
x-streamrank:
  polling_total_time_average: "1.7"
  polling_size_download_average: "1320517.68"
  streaming_total_time_average: "0.86"
  streaming_size_download_average: "662905.33"
  change_yes: "661"
  change_no: "1626"
  time_percentage: "49"
  size_percentage: "50"
  change_percentage: "29"
  last_run: "2018-05-12"
  days_run: "8"
  minute_run: "0"
---