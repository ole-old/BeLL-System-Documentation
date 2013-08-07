
{
	kind: "question",
	id: i8979kdfjfdk,
	type: "video-book",
	resourceId: 8796948,
	question: "Who is typing?",
	options: ["Leonard", "RJ", "The Cat"],
	answer: [2] // The key in the array of options
}

{
	kind: "sync",
	id: 64789g49085u09hg,
	resourceId: 1234588,
	createdBy: 84579e8fwhdfwei, // user ID
	group: 489357yhf98h94f8 // Group ID
	subject: "English",
	useContext: "Video book", // or Stories for Week, or Lesson
	configuration: {
		questions: [897887982, 87898787, 897897]
	}
}

{
	kind: "Feedback",
	id: 09876tfhdfjoe098,
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

{
	kind: "Group",
	id: 8763hf3j09fjn893fhb,
	owner: 083y5rh9f98h33, // Teacher's ID
	name: "Some group",
	level: "P3",
	members: [089hf9n9f8n, 089f9h4f9oh8n, 8f93h98o94hf] // Student IDs
}

{
	kind: "Member",
	role: "student",
	id: 09897e9gf9wvhe0w,
	pass: "998",
	level: "P2",
	dateRegistered: 109283743,
	dateOfBirth: 123984739,
	firstName: "",
	middleNames: "",
	lastName: ""
}


// This member did action to object at this time in this context
{
	kind:"action",
	memberId: "88789dio89779",
	role: "student",
	action: "view resource",
	object: "788dfd8977sdd897", 
	timestamp: 1228797
	context: "pbell" // pbell, lms
}

{
  kind: "Resource",
  id: "879dfd9879dfd879",
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

{
	kind: "Facility",
	id: "878dkdfj888dkd",
	type: "Basic School",
	GPS: ["lat", "lon"],
	name: "Katapor School",
	country: "",
	region: "",
	district: "",
	Area: "Katapor", // 
	street: ""
}









