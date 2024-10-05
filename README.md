# UXLab-Alexa


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

Let's say we create called "animal sounds", to use that skill we would need to tell alexa that the question we ask is directed to that particular skill.

A typical command to alexa looks like "Alexa, ask animal sounds to play a random bird sound"
- 'Alexa' is the wakeup word, once it hears this keyword it knows that the user is trying to communicate with it
- 'ask' is the starting phrase, there are more like 'launch', 'resume', 'run', 'begin', 'talk to', etc. These phrases indicate to alexa that you are about to name the skill you want to use. **THIS IS IMPORTANT**
- 'animal sounds' is the invocation name which is a unique identifier for your skill, it also happens to be the name of the skill but that is not necessary
- 'play a random bird sound' is called an utterance, this is what the user will say to use your skill, this will not be ideal and the users can use any words they want so we will have to understand the same meaning conveyed in all the different ways

There are 2 more parts of an alexa command that are more developer focused

- **Intents :** This is the logic of the code triggered when the user makes a request like 'play a random bird sound', this request triggers a behaviour which we can call 'BirdSoundintent', a single skill can have multiple intents.
	- This what we understand the user intends to do with our skill, from our skill animal sounds, there could be multiple intents such as getBirdSound or getCuteSound, how we bucket these is completely upto the developer.
- **Slots :** These are like additional information for us to use that might or might not be necessary, we can choose to handle a user request without any slots or double down and ask for more information if the user skips it.
	- Example: "Book me a ticket from portland to ohio on friday", in this case the slots and their respective fillers would be
	- fromCity : portland
	- toCity : ohio
	- travelDate : Friday which is then converted into an actual date using the nearest friday
