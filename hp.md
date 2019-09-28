History Provider (HP): Provides the EMF state history of whatever locations are specified.

Request Path Pattern: /locHistory?location={{location id}-{day}[{-another day}...]}
[_{{location id}-{day}[{- another day}...]}...]

Example: /locHistory?locations=sx100HIS-20190422-20190532_mjDD3H45-20190732_erTV5451-20191130-20191008

Maximum length of parameter "locations": 1024 UTF-8 characters
Maximum number of locations: 256
Maximum number of days for a locations: 32

HTTP response code 200: Success or failure
HTTP response code not 200: Fatal error

On failure response content could be anything
On success response content:

A JSON string providing the data requested:

{
Response: {some response code},
Data: [
	{
	Location: "sx100his",
	Name: "250 Lecture Theatre",
	DaysHistory: [
		{
		Day: "20190820",
		HoursHistory: [
			{State: 0, EndTime: "220455"}, ...
		]
		}, ...
	]
	}, ...
]
}

Possible values of "some response code":

rsp0: Request successfully carried out.
rsp1: Invalid request data.
rsp2: An error occured.
