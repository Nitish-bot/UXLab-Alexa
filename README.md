
### 30-09-24

FOCUS ON
- domain and learning outcomes
	- Physical: Motor skills, co-ordination, strength and flexibility. Encourages children to move their bodies
	- Cognitive Dev: Ability to think, reason and solve problems. Includes memory focus and understanding.
	- Socio-Emotional: understanding and managing emotions, developing self-regulation, building relationships, empathy, and cooperation.
	- Language and Literacy: reading, writing, listening, and speaking skills. also includes non verbal communication and literary skills like vocab and storytelling.
	- Aesthetic and cultural: the appreciation and creation of art, music, and cultural expressions. 
- competency
	- Guide kids to exercise run jump and just move, skill name could be "exercise routine" and could explain how to perform with proper form and play music to go along.
	- Age appropriate puzzles, memory games and sequences that challenge their reasoning and problem-solving ability.
	- Using group activities, role-plays or giving prompts using alexa that help facilitate conversation and help the child learn to express freely.
	- simple skill, alexa can read stories, poems and songs that will not only aid their hearing ability but also develop language and literary skills. (already exists)
	- activities like drawing, dancing and playing instruments. teach children about renowned artworks and stories. Teach them about how the world came to be.


How alexa can help

- simple story/poem narration ([exists](https://www.amazon.com/Amazon-Education-Consumer-Team-Storytime/dp/B073X5FYVF/ref=sr_1_1?dib=eyJ2IjoiMSJ9.S6bbH8KcsWWM7TPQd4YNjNQkAM4LPzW0ofFOB8lFxBEgAwxwUvptPiSSHlB4z9B14s6N59c57AxFMKPWKgYNeUZeloyVLMPt4f7z-cVvdLQKw6_xCUvblPM_DV74nb3WleDkmwQXCYFBBm9heoJ9wwILxs6qlC4wWsA8TgU-DA91GxgEMwkea_nwcjXgx-PuL--3--x8NmCl1ObEvfSGzdxUViKmDgPbe6zwOsEG3JY.h-tM7TuckLI6LqgLkON8Xh-YTwSMS4FyeFYHxyi5lxo&dib_tag=se&s=digital-skills&sr=1-1]))
- physical activity prompts like guiding exercise with form or some game
- Interactive age-appropriate conversations which encourage children to think and develop conversational skils
- spelling and grammar games maybe fill in the blanks that might help 
- ...


### 01/10/24 - Reading Alex Skill documentation 

[Principles of conversation design](https://developer.amazon.com/en-US/alexa/alexa-haus/design-principles)
- Signs of a good conversation experience
	- Conversation should have **low information density** since the user is probably going to be multi-tasking and it is possible they are not even looking at it.        { It applies even more so in our case since our users are children we would ideally like to keep it accessible to children without vision. }
	- Task should be faster with alexa than possible alternatives.        {I am not sure if this is a consideration in our case since we are working on an aid or I guess we automatically fall in that bracket. }
	- Task should be more fun.        { ✅ }
	- Answers should have high specificity.        { ✅ }
	- The task is commonly repeated.        { ✅ }
	- Choices (when given) should be restricted in number OR the user should have high level of comfort in knowing the choices.        { I think this implies for example, if we are asking math questions in a trivia, we would give options of up to four numbers to children aged 3 - 5 whereas we would probably not need to give options to an 8 year old }

- Three hallmarks of a task that is appropriate for conversation
	- Repeated usage
	- Restricted choices
	- Low variability

- [A great checklist for the conversations that we design](https://developer.amazon.com/en-US/alexa/alexa-haus/design-principles#conversation-design-principles-checklist)
	- Some of these checklist pointers might not apply to us since we are designing for kids and I am not sure how much of her personality alexa keeps. Because the checklist does not recommend we change her name or try to represent anyone other than amazon

_--_

[How to make our conversation sound natural](https://developer.amazon.com/en-US/alexa/alexa-haus/natural-speech)
- When designing dialog for Alexa Skills, focus on creating _spoken conversations_ rather than text meant to be read. Interactions should feel like chatting with a friend on the phone—natural, fluid, and easy to follow. People don’t speak like they write; we take turns, use shortforms, and often speak in bits and pieces.

- Questions should be at the end of sentence and you must make it explicit that that it is the user's turn to speak. Keep the questions to the end of the sentence and let them know if you will be asking multiple questions. [Great conversation examples](https://developer.amazon.com/en-US/alexa/alexa-haus/natural-speech#ask-questions)
	- Use progress markers like "Firstly, we will be doing xyz" or "Okay got it" to reaffirm the user that their input has been understood.
	- **Repeat the user input** so they can make sure alexa heard it correctly.

- Keep context and room for edge cases/ less than ideal answers
	- Let them over-answer as well as under-answer, take all the information if you have got it or ask again if they didnt give enough
	- Don't make them restate what they have already said
	- Hold context from previous sessions/ conversations
	- Don't be too obvious

- Use casual tone & grammar
	- Not everything we say in conversation is absolutely correct grammatically but that does not matter.
	- Speak in active voice.
	- Avoid jargons and formal language, use shortforms 
	- Use fewest words to convey most meaning

- Bring variability
	- Everytime a single task/skill is performed, it shouldn't repeat the same one thing, it could say hello, hi, or even a longer intro like "so what are we learning today?"
	- Use context to bring variability that uses information you already have to make their experience smoother

- Handle errors gracefully
	- No need to apologize everytime, you can say "would you repeat that one more time?", "sorry I wasn't listening"
	- If there is any ambiguity get it cleared immediately      { If user gives time as 8, ask if it is in the am or pm }

- Use SSML to add variance to volume, emphasis, breaks and speed of speech to make it sound more human like and not monotonous.


### 03-10-24 Continued documentation

How does Alexa interpret our language? because it doesn't understand words infact what it receives is a jumble of 0s and 1s, that is just noise. Thankfully alexa does all the interpretation for us and can detect with a great accuracy what words have been spoken.

Let's say we create a skill called "animal sounds", to use that skill we would need to tell alexa that the question we ask is directed to that particular skill.

A typical command to alexa looks like "Alexa, ask animal sounds to play a bird sound" 

##### Parts of a alexa command

Wake up word (handled by alexa)
- 'Alexa' is the wakeup word, once it hears this keyword it knows that the user is trying to communicate with it, this is when the microphone picks up and starts listening.

Starting phrase (handled by alexa)
- These phrases indicate to alexa that you are about to name the skill you want to use. 
- 'ask' is the starting phrase in our example, there are more like 'launch', 'open', 'resume', 'run', 'begin', 'talk to', etc. 

Invocation name (**THIS IS IMPORTANT**)
- 'animal sounds' is the invocation name which is a unique identifier for your skill.
- Name of skill is not the same as invocation name it just happens to be the name of the skill but that is not necessary. 
- Very important the invocation name has no alternate spellings or pronunciations and is as simple as can be. (example: whole and hole // heart beat and heartbeat)

Utterance
- 'play a bird sound' is called an utterance, this is what the user will say to use your skill, this will not be ideal and the users can use any words they want so we will have to understand the same meaning conveyed in all the different ways

	*This is the most painstaking task, we need to write down every utterance imaginable that should trigger the response we want to give, imagine every way a single request can be made and then add on to that how children would make them.
	Luckily once we have done this for one skill, it's much easier to do for the next thanks to overlaps*


There are 2 more parts of an alexa command that are more developer focused

**Intents :** 
- This is the logic of the code triggered when the user makes a request like 'play a bird sound', this request triggers a behaviour which we can call 'BirdSoundintent', a single skill can have multiple intents.
- User utterances map to user intents, and there can be and will be many utterances that all trigger the same utterance.
  eg: "what sound does a bird make" will trigger the same intent.
- This what we understand the user intends to do with our skill, from our skill animal sounds, there could be multiple intents such as getBirdSound or getRandomAnimalSound, how we bucket these is completely upto the developer.

**Slots :** 
- These are additional, variable information for us to use that might or might not be necessary, we can choose to handle a user request without any slots or double down and ask for more information if the user skips it. **These are part of the utterances.**
- In our example above 'play a bird sound', the user could also mention which bird they want to hear the sound of, that is a slot. Which gives us additional information required to fulfil the user request.

	*This is where we need room for edge cases, what if they provide the name of the bird, what if they don't, what questions do we ask in what way and then add variation to each of those questions to they don't sound monotonous*

- Example: "Book me a ticket from portland to ohio on friday", in this case the slots and their respective fillers would be
- fromCity : portland
- toCity : ohio
- travelDate : Friday which is then converted into an actual date using the nearest friday

### 08-10-24

Firstly, amazon has a set of guidelines that dictate the what skill can be directed towards children. The full policy can be found [here](https://developer.amazon.com/en-US/docs/alexa/custom-skills/policy-requirements-for-an-alexa-skill.html)

The most important thing for us to keep in mind is to try to **minimize our references to products or services outside of Alexa**, this specifically refers to brand names.
Besides that we **should not promote or sell anything** to the user and along with that we can not refer to other skills, except for our own.

Here is a summary of alexa's guide for children, you can find the full guide [here](https://developer.amazon.com/en-US/alexa/alexa-haus/child-directed-skills)

 Talk to kids in ways they understand
1. Kids are still learning to speak clearly. Alexa may struggle with mispronunciations, so only expect simple responses.
2. Kids might give unexpected answers or use words that make sense to them but not to adults. ****Refer to template to see why this is important
3. Your skill should be ready for these situations.

Avoid frustrating kids
1. Use simple, easy-to-say names for characters and places.
2. If Alexa can't understand a child, it can be upsetting for them.

Use words kids know
1. Avoid complex tech terms.
2. Keep language simple to prevent frustration.
3. Don't require specific phrases - allow for different ways of saying things.
4. For character names, include common mispronunciations as acceptable responses.

Be prepared to interpret when children need help
1. They can also be non-responsive, we need to have a conversation designed in that case. (eg: I didn't catch that, do you want me to repeat the question?)
2. Be prepared to hear "I don't know" and offer an alternate explanation or answer.

Children have low attention spans
1. Prompt them quick and prompt them often
2. Ask questions and give them a chance to input more frequently than might be necessary


Here is why all of these things are important, it is because when we design skills, we not only have to consider what 1 conversation flow will look like, we have to consider every one of them.
For example, if we are making a "Rhyming words chain" skill (Activity 2 that tanvi created) which will say a word and expect a rhyming word in return, then we need an entire conversation to be thought out and the following data to be noted:
- Greeting(s): It gets monotonous to hear the same set of words every time you turn on a skill, it makes it sound robotic, so we need a whole bunch of greetings that get chosen randomly to add variation. An example set would be:
  ("Hello kids, welcome to the rhyming chain", "Hello friends, ready to play a game?", "do you want to learn  how rhymes work?")

We should seriously consider making a lot of these in hindi since kids in our target age range will not be comfortable speaking let alone in english.


Additional things to consider

- Aside from that, the whole point of using alexa is to complete an activity from start to end, without using our hands or even sight in some cases, try to keep the **Materials Required** section as small as possible. (Also there can be a lack of resources with the end user so it will help if our activities don't require anything additional)


### 17-10-24

##### Alexa Conversations and Memory Management

### Conversational AI in Alexa

1. Alexa Conversations
   - A deep learning-based approach to dialog management
   - Allows for more natural, multi-turn conversations
   - Reduces the amount of code needed to handle complex dialogs

2. Key Features
   - Contextual understanding: Alexa can interpret user intents based on previous interactions
   - Slot filling: Automatically prompts for missing information
   - Dialog management: Handles conversation flow more naturally

### Remembering User Data

1. Session Attributes
   - Temporary storage for the duration of a session
   - Use for short-term memory within a single interaction
   - Example: Storing the current game score or the last question asked

2. Persistent Attributes
   - Long-term storage that persists across sessions
   - Use for remembering user preferences or progress
   - Stored in DynamoDB (Amazon's NoSQL database service)

3. User Profile API
   - Allows access to certain user information (with permissions)
   - Can retrieve data like name, email, phone number

4. Custom Data Storage
   - Implement your own database solution for more complex data storage
   - Options: Amazon S3, custom DynamoDB tables, or other database services

### Implementing Memory for Kids' Information

1. Initial Setup
   - Create a "profile creation" intent to gather basic info
   - Use slot filling to ask for name, age, and hobbies

2. Storing Data
   - Use persistent attributes to store profile information
   - Create a unique identifier for each child (e.g., based on the device ID)

3. Retrieving Data
   - At the start of each session, check if a profile exists
   - If it does, load the data and use it to personalize the interaction
   - If not, prompt to create a new profile or ask if it's a new user

4. Updating Information
   - Create intents to allow users to update their information
   - Implement periodic prompts to verify if the stored info is still current

### Potential AI Integration

1. Natural Language Understanding (NLU)
   - Improve intent recognition and slot filling
   - Better handle variations in children's speech patterns

2. Personalization
   - Use machine learning to adapt responses based on the child's age, interests, and interaction history
   - Customize difficulty levels or content topics

3. Sentiment Analysis
   - Detect the child's emotional state and adjust responses accordingly
   - Provide encouragement or change topics if the child seems frustrated

4. Content Generation
   - Use AI to generate age-appropriate stories, questions, or explanations
   - Create dynamic content that adapts to the child's interests

5. Speech Recognition Enhancement
   - Improve accuracy for children's voices and speech patterns
   - Handle mispronunciations and regional accents better

### Considerations and Challenges

1. Privacy and Security
   - Ensure compliance with children's privacy laws (e.g., COPPA)
   - Implement robust security measures for storing personal data

2. Ethical AI Use
   - Ensure AI-generated content is appropriate and safe for children
   - Avoid creating dependencies or excessive screen time

3. Scalability
   - Design the system to handle multiple users per device (e.g., siblings)
   - Ensure quick data retrieval and processing for smooth interactions

4. Testing and Iteration
   - Conduct extensive testing with diverse groups of children
   - Continuously gather feedback and improve the conversation flow

Remember: When implementing these features, always prioritize the child's privacy, safety, and well-being. Ensure all data collection and AI interactions comply with relevant regulations and Alexa's policies for child-directed skills.
