# AWS_IoT_Policy

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "iot:Connect"
      ],
      "Resource": [
        "arn:aws:iot:*:*:client/*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "iot:Publish",
        "iot:Receive"
      ],
      "Resource": [
        "arn:aws:iot:*:*:topic/*",
        "arn:aws:iot:*:*:topic/$aws/things/${iot:Connection.Thing.ThingName}/*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "iot:Subscribe"
      ],
      "Resource": [
        "arn:aws:iot:*:*:topicfilter/${iot:Connection.Thing.ThingName}/*",
        "arn:aws:iot:*:*:topicfilter/$aws/things/${iot:Connection.Thing.ThingName}/*",
        "*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "iot:UpdateThingShadow",
        "iot:GetThingShadow"
      ],
      "Resource": [
        "arn:aws:iot:*:*:thing/${iot:Connection.Thing.ThingName}"
      ]
    }
  ]
}
