# Question

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

# Assignment

```js
{
  kind: "Assignment",
  resourceId: <% Resource _id %>,
  createdBy: <% Member _id %>, 
  startDate: <% Unix timestamp %>,
  endDate: <% Unix timestamp %>,
  targetDate: <% Unix timestamp %>
  context: {
    subject: "English",
    use: "Video book", // or Stories for Week, or Lesson
    groupId: <% Group _id %>,
    facilityId: <% Facility _id %>
  }
  configuration: {
    questions: [<% Question _id %>, <% Question _id %>, ...]
  }
}
```

# Feedback

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

# Group

```js
{
  kind: "Group",
  facility: <% Facility _id %>,
  owner: [<% Member _id %>, ...], // Teacher IDs
  name: "Some group",
  levels: ["P3", ...],
  members: [<% Member _id %>, ...] // Student IDs
}
```

# Member

When moving to other systems, user should create account again by matching the id and date of birth. This process will change their facility, login and pass will only be unique for a facility, so now with their record modified for the facility, their login and pass will work. That gives a chance to check the uniqueness at the facility.  This has two advantages: convenience because the user may make a typo when typing the id and which might be another record, a nonmatching birth date would be raise a red flag; for security, if they bring their account to a service online, then bots would have to get guess both an id and a birthday combination which would be much harder. 

```js
{
  kind: "Member",
  facility: <% Facility _id %> // Facility ID
  login: “RJ”, // Unique for facility, not across network
  role: [<% "student" || "teacher" || "head" || "lead" || "coach" %>,  ... ],
  pass: "998",
  gender: "<% male || female || other %>",
  levels: ["P2", ...],
  dateRegistered: <% Unix timestamp %>,
  dateOfBirth: <% Unix timestamp %>,
  status: "active", // active, inactive, deceased  
  firstName: "Bob",
  middleNames: "James",
  lastName: "Stein",
  phone: "8888888888",
  _attachments: { <% profile image files %> }
}
```

# Action

This Action.member did Action.action to Action.objectId at Action.timestamp in Action.context

```js
{
  kind:"Action",
  memberId: <% Member _id %>,
  memberRoles: ["student", ...], // Member doing Action may have many roles
  action: "view resource",
  objectId: <% Object _id %>, 
  timestamp: <% Unix timestamp %>
  context: "pbell" // pbell, lms, ...
}
```

# Resource 

```js
{
  kind: "Resource",
  type: <% "Video Book" || "Readable" || "Video Tutorial" || "Audio Lesson" %>,
  audience: [<% "teacher training" || "health" || "community education" || "formal education" %>, ...],
  title: "Good Book",
  author: "Jane Gong", 
  language: <% Language code %>,
  subject: ["English", "Literature", "Math", "Science", "Environmental Studies", ...],
  description: "This book is a good read.",
  uploadDate: <% Unix timestamp %>,
  levels:  ["KG", "P1", ...],
  approvedBy: ["School", "OLE", "Government", ...],
  uploadedBy: <% Member _id %>, 
  _attachment: { <% resource files %> }
}
```

# Facility

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
  street: "",
  dateEnrolled:"<% unix timestamp%>"
}

```

# whoami/config
```js
{
  id: "config",
  kind: "system",
  timezone: <% Timezone Abbreviation %>,
  language: <% Language Code %>,
  version: <% BeLL LMS Version Number %>,
  layout: <% Numberic value indicating which text layout is used %>,
  subjects: <% array of subjects for the Subjects vocabulary at this facility %>,
  levels: <% array of Levels for the Levels vocabulary at this facility %>
}
```

# whoami/facility
```js
{
  facilityId: <% Facility _id %>
}
```
