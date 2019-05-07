# ![LOGO](logo.png) GoToWebinar **flow**ground Connector

## Description

A generated **flow**ground connector for the GoToWebinar API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/getgo.com/gotowebinar/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:40:53+03:00

## API Description

The GoToWebinar API provides seamless integration of webinar registrant and attendee data into your existing infrastructure or third-party applications. The ability to register participants, as well as pull lists of registrants and attendees for a webinar, allows organizers to manage the flow of information between their primary applications without manual intervention.

## Authorization

This API does not require authorization.

## Actions

### Get all webinars for an account

> Retrieves the list of webinars for an account within a given date range. __*Page*__ and __*size*__ parameters are optional. Default __*page*__ is 0 and default __*size*__ is 20. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `accountKey` - _required_ - The key of the account
* `fromTime` - _required_ - A required start of datetime range in ISO8601 UTC format, e.g. 2015-07-13T10:00:00Z
* `toTime` - _required_ - A required end of datetime range in ISO8601 UTC format, e.g. 2015-07-13T22:00:00Z
* `page` - _optional_ - The page number to be displayed. The first page is 0.
* `size` - _optional_ - The size of the page.

### Get historical webinars

> Returns details for completed webinars for the specified organizer and completed webinars of other organizers where the specified organizer is a co-organizer.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `fromTime` - _required_ - A required start of datetime range in ISO8601 UTC format, e.g. 2015-07-13T10:00:00Z
* `toTime` - _required_ - A required end of datetime range in ISO8601 UTC format, e.g. 2015-07-13T22:00:00Z

### Get organizer sessions

> Retrieve all completed sessions of all the webinars of a given organizer.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `fromTime` - _required_ - A required start of datetime range in ISO8601 UTC format, e.g. 2015-07-13T10:00:00Z
* `toTime` - _required_ - A required end of datetime range in ISO8601 UTC format, e.g. 2015-07-13T22:00:00Z

### Get upcoming webinars

> Returns webinars scheduled for the future for the specified organizer and webinars of other organizers where the specified organizer is a co-organizer.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer

### Get all webinars

> Returns webinars scheduled for the future for a specified organizer.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer

### Create webinar

> Creates a single session webinar, a sequence of webinars or a series of webinars depending on the type field in the body: "single_session" creates a single webinar session, "sequence" creates a webinar with multiple meeting times where attendees are expected to be the same for all sessions, and "series" creates a webinar with multiple meetings times where attendees choose only one to attend. The default, if no type is declared, is single_session. A sequence webinar requires a "recurrenceStart" object consisting of a "startTime" and "endTime" key for the first webinar of the sequence, a "recurrencePattern" of "daily", "weekly", "monthly", and a "recurrenceEnd" which is the last date of the sequence (for example, 2016-12-01). A series webinar requires a "times" array with a discrete "startTime" and "endTime" for each webinar in the series. The call requires a webinar subject and description. The "isPasswordProtected" sets whether the webinar requires a password for attendees to join. If set to True, the organizer must go to Registration Settings at My Webinars (https://global.gotowebinar.com/webinars.tmpl) and add the password to the webinar, and send the password to the registrants. The response provides a numeric webinarKey in string format for the new webinar. Once a webinar has been created with this method, you can accept registrations.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer

### Cancel webinar

> Cancels a specific webinar. If the webinar is a series or sequence, this call deletes all scheduled sessions. To send cancellation emails to registrants set sendCancellationEmails=true in the request. When the cancellation emails are sent, the default generated message is used in the cancellation email body.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sendCancellationEmails` - _optional_ - Indicates whether cancellation notice emails should be sent. The default value is false

### Get webinar

> Retrieve information on a specific webinar. If the type of the webinar is 'sequence', a sequence of future times will be provided. Webinars of type 'series' are treated the same as normal webinars - each session in the webinar series has a different webinarKey. If an organizer cancels a webinar, then a request to get that webinar would return a '404 Not Found' error.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Update webinar

> Updates a webinar. The call requires at least one of the parameters in the request body. The request completely replaces the existing session, series, or sequence and so must include the full definition of each as for the Create call. Set notifyParticipants=true to send update emails to registrants.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `notifyParticipants` - _optional_ - Defines whether to send notifications to participants

### Get attendees for all webinar sessions

> Returns all attendees for all sessions of the specified webinar.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Get audio information

> Retrieves the audio/conferencing information for a specific webinar.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Update audio information

> Updates the audio/conferencing settings for a specific webinar

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `notifyParticipants` - _optional_ - Defines whether to send notifications to participants

### Get co-organizers

> Returns the co-organizers for the specified webinar. The original organizer who created the webinar is filtered out of the list. If the webinar has no co-organizers, an empty array is returned. Co-organizers that do not have a GoToWebinar account are returned as external co-organizers. For those organizers no surname is returned.

*Tags:* `Co-organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Create co-organizers

> Creates co-organizers for the specified webinar. For co-organizers that have a GoToWebinar account you have to set the parameter 'external' to 'false'. In this case you have to pass the parameter 'organizerKey' only. For co-organizers that have no GoToWebinar account you have to set the parameter 'external' to 'true'. In this case you have to pass the parameters 'givenName' and 'email'. Since there is no parameter for 'surname' you should pass first and last name to the parameter 'givenName'.

*Tags:* `Co-organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Delete co-organizer

> Deletes an internal co-organizer specified by the coorganizerKey (memberKey).

*Tags:* `Co-organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `coorganizerKey` - _required_ - The key of the internal or external co-organizer (memberKey)
* `external` - _optional_ - By default only internal co-organizers (with a GoToWebinar account) can be deleted. If you want to use this call for external co-organizers you have to set this parameter to 'true'.

### Resend invitation

> Resends an invitation email to the specified co-organizer

*Tags:* `Co-organizers`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `coorganizerKey` - _required_ - The key of the internal or external co-organizer (memberKey)
* `external` - _optional_ - By default only internal co-organizers (with a GoToWebinar account) will retrieve the resent invitation email. If you want to use this call for external co-organizers you have to set this parameter to 'true'.

### Get webinar meeting times

> Retrieves the meeting times for a webinar.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Get webinar panelists

> Retrieves all the panelists for a specific webinar.

*Tags:* `Panelists`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Create Panelists

> Create panelists for a specified webinar

*Tags:* `Panelists`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Delete webinar panelist

> Removes a webinar panelist.

*Tags:* `Panelists`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `panelistKey` - _required_ - The key of the webinar panelist

### Resend panelist invitation

> Resend the panelist invitation email.

*Tags:* `Panelists`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `panelistKey` - _required_ - The key of the webinar panelist

### Get performance for all webinar sessions

> Gets performance details for all sessions of a specific webinar.

*Tags:* `Webinars`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Get registrants

> Retrieve registration details for all registrants of a specific webinar. Registrant details will not include all fields captured when creating the registrant. To see all data, use the API call 'Get Registrant'. Registrants can have one of the following states; <br>WAITING - registrant registered and is awaiting approval (where organizer has required approval), <br>APPROVED - registrant registered and is approved, and <br>DENIED - registrant registered and was denied.

*Tags:* `Registrants`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Create registrant

> Register an attendee for a scheduled webinar. The response contains the registrantKey and join URL for the registrant. An email will be sent to the registrant unless the organizer turns off the confirmation email setting from the GoToWebinar website. Please note that you must provide all required fields including custom fields defined during the webinar creation. Use the API call 'Get registration fields' to get a list of all fields, if they are required, and their possible values. At this time there are two versions of the 'Create Registrant' call. The first version only accepts firstName, lastName, and email and ignores all other fields. If you have custom fields or want to capture additional information this version won't work for you. The second version allows you to pass all required and optional fields, including custom fields defined when creating the webinar. To use the second version you must pass the header value 'Accept: application/vnd.citrix.g2wapi-v1.1+json' instead of 'Accept: application/json'. Leaving this header out results in the first version of the API call.

*Tags:* `Registrants`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `Accept` - _optional_ - Set to 'application/vnd.citrix.g2wapi-v1.1+json' to make a registration using fields (custom or default) additional to the basic ones.
* `resendConfirmation` - _optional_ - Indicates whether the confirmation email should be resent when a registrant is re-registered. The default value is false.

### Get registration fields

> Retrieve required, optional registration, and custom questions for a specified webinar.

*Tags:* `Registrants`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Delete registrant

> Removes a webinar registrant from current registrations for the specified webinar. The webinar must be a scheduled, future webinar.

*Tags:* `Registrants`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `registrantKey` - _required_ - The key of the registrant

### Get registrant

> Retrieve registration details for a specific registrant.

*Tags:* `Registrants`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `registrantKey` - _required_ - The key of the registrant

### Get webinar sessions

> Retrieves details for all past sessions of a specific webinar.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar

### Get webinar session

> Retrieves attendance details for a specific webinar session that has ended. If attendees attended the session ('registrantsAttended'), specific attendance details, such as attendenceTime for a registrant, will also be retrieved. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session

### Get session attendees

> Retrieve details for all attendees of a specific webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Attendees`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session

### Get attendee

> Retrieve registration details for a particular attendee of a specific webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Attendees`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session
* `registrantKey` - _required_ - The key of the registrant

### Get attendee poll answers

> Get poll answers from a particular attendee of a specific webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Attendees`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session
* `registrantKey` - _required_ - The key of the registrant

### Get attendee questions

> Get questions asked by an attendee during a webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Attendees`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session
* `registrantKey` - _required_ - The key of the registrant

### Get attendee survey answers

> Retrieve survey answers from a particular attendee during a webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Attendees`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session
* `registrantKey` - _required_ - The key of the registrant

### Get session performance

> Get performance details for a session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session

### Get session polls

> Retrieve all collated attendee questions and answers for polls from a specific webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session

### Get session questions

> Retrieve questions and answers for a past webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session

### Get session surveys

> Retrieve surveys for a past webinar session. For technical reasons, this call cannot be executed from this documentation. Please use the curl command to execute it.

*Tags:* `Sessions`

#### Input Parameters
* `Authorization` - _required_ - Access token
* `organizerKey` - _required_ - The key of the organizer
* `webinarKey` - _required_ - The key of the webinar
* `sessionKey` - _required_ - The key of the webinar session

## License

**flow**ground :- Telekom iPaaS / getgo-com-gotowebinar-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
