```js
{
	kind: "Question",
	type: "video-book",
	resourceId: <% Resource _id %>,
	question: "Who is typing?",
	options: ["Leonard", "RJ", "The Cat"],
	answer: [2, ...] // The key in the array of options, there might be many answers
}
```

```js
{
	kind: "Assignment",
	resourceId: <% Resource _id %>,
	createdBy: <% Member _id %>, 
	startDate: <% Unix timestamp %>,
	endDate: <% Unix timestamp %>,
	context: {
	  subject: "English",
		use: "Video book", // or Stories for Week, or Lesson
		group: <% Group _id %>
	}
	configuration: {
		questions: [<% Question _id %>, <% Question _id %>, ...]
	}
}
```

```js
{
	kind: "Feedback",
	rating: 4,
	comment: "Some comment",
  resourceId: <% Resource _id %>,
  created: <% Unix timestamp %>,
  context: {
  	subject: "English",
  	use: "Stories for the week",
  	level: "P3" // This can be derived from the level of the Group
	}
	// @todo Do we want to include the Questions used in configuration?
}
```

```js
{
	kind: "Group",
	facility: <% Facility _id %>,
	owner: [<% Member _id %>, ...], // Teacher IDs
	name: "Some group",
	level: "P3",
	members: [<% Member _id %>, ...] // Student IDs
}
```

When moving to other systems, user should create account again by matching the id and date of birth. This process will change their facility, login and pass will only be unique for a facility, so now with their record modified for the facility, their login and pass will work. That gives a chance to check the uniqueness at the facility.  This has two advantages: convenience because the user may make a typo when typing the id and which might be another record, a nonmatching birth date would be raise a red flag; for security, if they bring their account to a service online, then bots would have to get guess both an id and a birthday combination which would be much harder. 

```js
{
	kind: "Member",
	facility: <% Facility _id %> // Facility ID
	login: “RJ”, // Unique for facility, not across network
	role: ["student", ...],
	pass: "998",
	level: "P2",
	dateRegistered: <% Unix timestampt %>,
	dateOfBirth: <% Unix timestampt %>,
	firstName: "Bob",
	middleNames: "James",
	lastName: "Stein"
	_attachments: { <% profile image files %> }
}
```


This member did action to object at this time in this context

```js
{
	kind:"Action",
	memberId: <% Member _id %>,
	role: "student",
	action: "view resource",
	object: <% Object _id %>, 
	timestamp: <% Unix timestamp %>
	context: "pbell" // pbell, lms, ...
}
```

```js
{
  kind: "Resource",
  type: "Video Book", // Readable, Video Tutorial, Audio Lesson
  audience: ["teacher training", "health", "community education", "formal education", ...]
  title: "Good Book",
  author: "Jane Gong", 
  subject: ["English", "Literature", "Math", "Science", "Environmental Studies", ...],
  description: "This book is a good read.",
  uploadTimestamp: <% Unix timestampt %>,
  levels:  ["KG", "P1", ...],
  approvedBy: ["School", "OLE", "Government", ...],
  uploadedBy: <% Member _id %>, 
  _attachment: { <% resource files %> }
}
```

```js
{
	kind: "Facility",
	type: "Basic School",
	GPS: ["<% lat %>", "<% lon %>"],
	name: "Katapor School",
	country: "",
	region: "",
	district: "",
	area: "Katapor", // 
	street: ""
}

```
