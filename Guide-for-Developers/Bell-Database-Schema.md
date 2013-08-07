```js
{
	kind: "Question",
	type: "video-book",
	resourceId: 8796948,
	question: "Who is typing?",
	options: ["Leonard", "RJ", "The Cat"],
	answer: [2] // The key in the array of options
}
```

```js
{
	kind: "Sync",
	resourceId: 1234588,
	createdBy: 84579e8fwhdfwei, // user ID
	group: 489357yhf98h94f8 // Group ID
	subject: "English",
	useContext: "Video book", // or Stories for Week, or Lesson
	configuration: {
		questions: [897887982, 87898787, 897897]
	}
}
```

```js
{
	kind: "Feedback",
	rating: 4,
	comment: "Some comment",
  resourceId: 394r5935393r3jf34998,
  timestamp: 122394848,
  context: {
  	subject: "English",
  	use: "Stories for the week",
  	level: "P3"
	}
}
```

```js
{
	kind: "Group",
	id: 8763hf3j09fjn893fhb,
	facility: “784995985h97g9e8hf98”,
	owner: [083y5rh9f98h33, 8021887741228], // Teacher's ID
	name: "Some group",
	level: "P3",
	members: [08hf9n9f8n, 089f9h4f9oh8n, 89f93h98o94hf] // Student IDs
}
```

When moving to other systems, user should create account again by matching the id and date of birth. This process will change their facility, login and pass will only be unique for a facility, so now with their record modified for the facility, their login and pass will work. That gives a chance to check the uniqueness at the facility.  This has two advantages: convenience because the user may make a typo when typing the id and which might be another record, a nonmatching birth date would be raise a red flag; for security, if they bring their account to a service online, then bots would have to get guess both an id and a birthday combination which would be much harder. 

```js
{
	kind: "Member",
	facility: “87887df878dd87” // Facility ID
	login: “RJ”, // Unique for facility, not across network
	role: ["student"],
	pass: "998",
	level: "P2",
	dateRegistered: 109283743,
	dateOfBirth: 123984739,
	firstName: "",
	middleNames: "",
	lastName: ""
	_attachments: { Profile images }
}
```


This member did action to object at this time in this context

```js
{
	kind:"Action",
	memberId: "88789dio89779",
	role: "student",
	action: "view resource",
	object: "788dfd8977sdd897", 
	timestamp: 1228797
	context: "pbell" // pbell, lms
}
```

```js
{
  kind: "Resource",
  type: "Video Book", // Readable, Video Tutorial, Audio Lesson
  audience: ["teacher training", "health", "community education", "formal education"]
  title: "Good Book",
  author: "Jane McGonal", 
  subject: ["English", "Literature", "Math", "Science", "Environmental Studies"],
  description: "This book is a good read.",
  uploadTimestamp:1288754887000,
  levels:  ["KG", "P1", ...],
  approvedBy: ["School", "OLE", "Government"],
  uploadedBy: "87587idfudik" // Member ID
  _attachment: {...}
}
```

```js
{
	kind: "Facility",
	type: "Basic School",
	GPS: ["lat", "lon"],
	name: "Katapor School",
	country: "",
	region: "",
	district: "",
	Area: "Katapor", // 
	street: ""
}

```
