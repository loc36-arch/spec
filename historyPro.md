History Provider: Provides the EMF state history of whatever locations are specified.

Request Path Pattern: /locHistory?location={{location id}-{day}[{-another day}...]}
[_{{location id}-{day}[{- another day}...]}...]

Example: /locHistory?locations=sx100HIS-20190422-20190532_mjDD3H45-20190732_erTV5451-20191130-20191008

HTTP response code not 200: Fatal error
HTTP response code 200: Success or failure


On failure response content could be anything
On success response content:

a JSON string providing the data requested

{
Response: {some response code},
Data: [
	{
	ID: "sx100his",
	Name: "250 Lecture Theatre",
	History: [
		{
		Day: "20190820",
		History: [
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
