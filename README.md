<h1 align="center">  
AgenticAI-DialogGen: Topic-guided Conversation Generation for Fine-tuning and Evaluating Long-term Memory of LLMs
</h1>  


## **TopicGuidedChat (TGC) Dataset — Sample Release**

This repository contains a sample version of the TopicGuidedChat (TGC) dataset generated via the AgenticAI-DialogGen framework described in our paper* entitled, “AgenticAI-DialogGen: Topic-guided Conversation Generation for Fine-tuning and Evaluating Long-term Memory of LLMs”. The TGC dataset is a large-scale synthetic benchmark derived from the [Multi-Session Chat (MSC) dataset](https://aclanthology.org/2022.acl-long.356/) and is designed to support research on fine-tuning and evaluating the long-term memory of LLMs.

## **Publication Status**

_This paper* has been submitted to ACL 2026 and is currently under review. This repository provides only a sample to illustrate the dataset schema and content. The complete version of the dataset will be released after the paper review process._


## **About the TGC Dataset**

Conversations are organized by topics, thereby enabling precise modeling of topic coherence and memory grounding.

For each speaker pair, the dataset includes:
-  Up to 3 topics.
-  14 conversational turns for each topic as short-term memory.
-  Speaker-specific knowledge graphs as long-term memory derived from MSC dataset conversations.
-  20 Memory-grounded QA pairs per topic probing both short- and long-term memory.

At full scale, the dataset comprises:
- 1,001 persona profiles.
- 4,004 conversations totaling 94,520 conversational turns.
- 2,985 topic instances across conversations.
- 146,237 speaker-wise knowledge graphs.
- 59,700 QA pairs for memory evaluation.

## 🤖 **About the AgenticAI-DialogGen Framework**

AgenticAI-DialogGen is a modular agent-based framework for generating topic-guided and persona grounded conversations without human annotation. The framework extracts knowledge from the MSC dataset, organizes it into coherent topics, and constructs speaker-specific knowledge graphs. Leveraging LLM agents, it simulates realistic multi-turn conversations which are then validated, refined, and enriched with memory-grounded QA pairs to support both short- and long-term memory evaluation.

## 📂 Sample of the TGC Dataset

Below is a snippet showing the dataset structure for a **single topic** with **speaker-wise knowledge graphs** and **newly generated conversational turns**.

```json

    {
        "topic": "Cooking and Food Preferences",
        "participants": [
            "speaker1",
            "speaker2"
        ],
        "personas": [
            {
                "speaker_id": "speaker1",
                "background_facts": [
                    {
                        "subject": "speaker1",
                        "relation": "like to do",
                        "object": "canning",
                        "source_turn": 2
                    },
                    {
                        "subject": "speaker1",
                        "relation": "eats exclusively",
                        "object": "favorite meat",
                        "source_turn": 6
                    },
                    {
                        "subject": "speaker1",
                        "relation": "would have to say",
                        "object": "its prime rib",
                        "source_turn": 8
                    },
                    {
                        "subject": "speaker1",
                        "relation": "think",
                        "object": "speaker1 is going to do some canning",
                        "source_turn": 10
                    },
 
                    {
                        "subject": "speaker1",
                        "relation": "thinks",
                        "object": "speaker1 will can some jam",
                        "source_turn": 12
                    },
                    {
                        "subject": "speaker1",
                        "relation": "likes",
                        "object": "deer meat",
                        "source_turn": 19
                    },
                    {
                        "subject": "speaker2",
                        "relation": "asks about",
                        "object": "speaker1's favorite meals",
                        "source_turn": 21
                    },
                    {
                        "subject": "speaker1",
                        "relation": "loves",
                        "object": "meat",
                        "source_turn": 22
                    },
                    {
                        "subject": "speaker1",
                        "relation": "favourite food",
                        "object": "meat",
                        "source_turn": 22
                    },
                    {
                        "subject": "speaker1's wife",
                        "relation": "likes",
                        "object": "chicken",
                        "source_turn": 22
                    },
                    {
                        "subject": "speaker1's wife's recipe",
                        "relation": "is",
                        "object": "Thai chicken with rice",
                        "source_turn": 22
                    },
                    {
                        "subject": "speaker1",
                        "relation": "tried",
                        "object": "that jerk chicken recipe",
                        "source_turn": 26
                    },
                    {
                        "subject": "speaker1",
                        "relation": "loves to eat",
                        "object": "a lot of meat",
                        "source_turn": 28
                    }
                ]
              
            },
            {
                "speaker_id": "speaker2",
                "background_facts": [
                    {
                        "subject": "speaker2",
                        "relation": "likes",
                        "object": "chicken",
                        "source_turn": 9
                    },
                    {
                        "subject": "speaker2",
                        "relation": "likes",
                        "object": "macaroni and cheese",
                        "source_turn": 9
                    },
                    {   "subject": "speaker2", 
                        "relation": "thinks", 
                        "object": "deer meat makes good jerky", 
                        "source_turn": 21 
                    },
		    {   "subject": "speaker2", 
                        "relation": "not favorite", 
                        "object": "deer meat", 
                        "source_turn": 21 
                     }
                    {
                        "subject": "speaker2",
                        "relation": "asks about",
                        "object": "speaker1's favorite meals",
                        "source_turn": 21
                    },
                    {   "subject": "speaker2", 
                        "relation": "favorite dish", 
                        "object": "jerk chicken with red beans and rice", 
                        "source_turn": 23 
		    },
                    {   "subject": "speaker2", 
		        "relation": "is a big fan of", 
                        "object": "mac n' cheese", 
                        "source_turn": 23 
		    },
                    {
                        "subject": "speaker2",
                        "relation": "needs to send",
                        "object": "speaker1 the recipe for jerk chicken",
                        "source_turn": 24
                    },
    		    {   "subject": "speaker2", 
                        "relation": "has recipe for", 
                        "object": "jerk chicken", 
                        "source_turn": 25 
                    }

                
                ]
            }
        ],
        "turns": [
            {
                "speaker": "speaker1",
                "text": "I love cooking and trying new recipes. Meat is definitely my favorite thing to eat. I especially enjoy canning jams and preserving foods. Do you have a favorite dish or type of meat you like?",
                "turn_number": 1
            },
            {
                "speaker": "speaker2",
                "text": "That sounds fun! I really like chicken and macaroni and cheese. They’re comfort foods for me. Do you have a favorite recipe you like to make?",
                "turn_number": 2
            },
            {
                "speaker": "speaker1",
                "text": "I do love a good prime rib. It’s my go-to for special occasions. I also enjoy canning some jam when I get the chance. Do you ever try making your own jams or preserves?",
                "turn_number": 3
            },
            {
                "speaker": "speaker2",
                "text": "I haven't tried making my own jams yet, but I’d love to learn. Do you have a favorite jam recipe you could share?",
                "turn_number": 4
            },
            {
                "speaker": "speaker1",
                "text": "Absolutely. I like to make strawberry or peach jam. I use fresh fruit and a good amount of sugar. It’s simple but really tasty. Do you like any particular fruit for jam?",
                "turn_number": 5
            },
            {
                "speaker": "speaker2",
                "text": "I really like making mango or blueberry jam. They have such vibrant flavors. If you want, I can send you my favorite recipe for jerk chicken too.",
                "turn_number": 6
            },
            {
                "speaker": "speaker1",
                "text": "That sounds delicious. I’ve tried jerk chicken before, and I loved the bold flavors. I’d definitely like to see your recipe. Do you usually make it spicy or milder?",
                "turn_number": 7
            },
            {
                "speaker": "speaker2",
                "text": "I like it spicy. The heat really brings out the flavors. I’d love to see your recipe.",
                "turn_number": 8
            },
            {
                "speaker": "speaker1",
                "text": "Great! I’ll send you my recipe for jerk chicken. I like to keep it pretty spicy too. The heat really makes the flavors pop. Do you usually serve it with rice or something else?",
                "turn_number": 9
            },
            {
                "speaker": "speaker2",
                "text": "I usually serve jerk chicken with rice and peas. Sometimes I add a side of plantains too. It’s a really tasty combo. Do you have a favorite side dish to go with it?",
                "turn_number": 10
            },
            {
                "speaker": "speaker1",
                "text": "I love pairing jerk chicken with rice and peas too. Sometimes I add a little coleslaw on the side. It’s a nice crunch to go with the spicy chicken. Do you like to make your own plantains or buy them ready-made?",
                "turn_number": 11
            },
            {
                "speaker": "speaker2",
                "text": "I usually buy ready-made plantains. It’s easier and they still taste great. Do you like to fry your plantains or prepare them some other way?",
                "turn_number": 12
            },
            {
                "speaker": "speaker1",
                "text": "I usually fry my plantains. I like them nice and golden. They get a great sweetness when fried. Do you prefer them baked or grilled sometimes?",
                "turn_number": 13
            },
            {
                "speaker": "speaker2",
                "text": "I mostly fry my plantains too. They turn out so crispy and sweet. Sometimes I bake them if I want a healthier option. Grilled plantains are good too, especially with a smoky flavor. Do you ever try grilling them?",
                "turn_number": 14
            }
        ],
       
        
        "qa_pairs": [
            {
                "question_id": 1,
                "question": "What’s my favorite meat to cook for special occasions?",
                "answer": "Prime rib"
            },
            {
                "question_id": 2,
                "question": "Which type of meat, besides prime rib, do I enjoy?",
                "answer": "Deer"
            },
            {
                "question_id": 3,
                "question": "Have I ever tried canning jams?",
                "answer": "Yes"
            },
            {
                "question_id": 4,
                "question": "Does my wife prefer a particular type of meat?",
                "answer": "Yes, chicken"
            },
            {
                "question_id": 5,
                "question": "What’s my wife’s favorite chicken recipe?",
                "answer": "Thai chicken"
            },
            {
                "question_id": 6,
                "question": "Did I like the jerk chicken recipe I tried?",
                "answer": "Yes"
            },
            {
                "question_id": 7,
                "question": "How spicy do I make my jerk chicken?",
                "answer": "Very spicy"
            },
            {
                "question_id": 8,
                "question": "What side dish do I add for crunch?",
                "answer": "Coleslaw"
            },
            {
                "question_id": 9,
                "question": "Which fruit do I prefer for canning jams?",
                "answer": "Strawberry or peach"
            },
            {
                "question_id": 10,
                "question": "How do I usually prepare plantains?",
                "answer": "Fried"
            },
            {
                "question_id": 11,
                "question": "Do I ever make my own jam preserves?",
                "answer": "Yes"
            },
            {
                "question_id": 12,
                "question": "Have I tried jerk chicken before?",
                "answer": "Yes"
            },
            {
                "question_id": 13,
                "question": "What sweetener do I use in my jams?",
                "answer": "Sugar"
            },
            {
                "question_id": 14,
                "question": "Which side do I like with rice and peas?",
                "answer": "Plantains"
            },
            {
                "question_id": 15,
                "question": "Do I ever grill my plantains?",
                "answer": "Yes, sometimes"
            },
            {
                "question_id": 16,
                "question": "What jerk chicken flavors do I like?",
                "answer": "Bold flavors"
            },
            {
                "question_id": 17,
                "question": "Which jam recipe would I recommend?",
                "answer": "Strawberry or Peach"
            },
            {
                "question_id": 18,
                "question": "Have I ever paired jerk chicken with anything else?",
                "answer": "Rice and peas"
            },
            {
                "question_id": 19,
                "question": "Which method do I prefer: baking or frying plantains?",
                "answer": "Frying"
            },
            {
                "question_id": 20,
                "question": "What's the key ingredient in my jam recipes?",
                "answer": "Fresh fruit"
            }
        ]
    }
 ],
        "msc_turns": [
            {
                "user_id": "032bbc38",
                "text": "Hi, how are you doing? I'm getting ready to do some cheetah chasing to stay in shape."
            },
            {
                "user_id": "63786412",
                "text": "You must be very fast. Hunting is one of my favorite hobbies."
            },
            {
                "user_id": "032bbc38",
                "text": "I am! For my hobby I like to do canning or some whittling."
            },
            {
                "user_id": "63786412",
                "text": "I also remodel homes when I am not out bow hunting."
            },
            {
                "user_id": "032bbc38",
                "text": "That's neat. When I was in high school I placed 6th in 100m dash!"
            },
            {
                "user_id": "63786412",
                "text": "That's awesome. Do you have a favorite season or time of year?"
            },
            {
                "user_id": "032bbc38",
                "text": "I do not. But I do have a favorite meat since that is all I eat exclusively."
            },
            {
                "user_id": "63786412",
                "text": "What is your favorite meat to eat?"
            },
            {
                "user_id": "032bbc38",
                "text": "I would have to say its prime rib. Do you have any favorite foods?"
            },
            {
                "user_id": "63786412",
                "text": "I like chicken or macaroni and cheese."
            },
            {
                "user_id": "032bbc38",
                "text": "Do you have anything planned for today? I think I am going to do some canning."
            },
            {
                "user_id": "63786412",
                "text": "I am going to watch football. What are you canning?"
            },
            {
                "user_id": "032bbc38",
                "text": "I think I will can some jam. Do you also play footfall for fun?"
            },
            {
                "user_id": "63786412",
                "text": "If I have time outside of hunting and remodeling homes. Which is not much!"
            },
            {
                "user_id": "63786412",
                "text": "Did you get to do any bow hunting lately?"
            },
            {
                "user_id": "63786412",
                "text": "No, the weather was poor, hoping to reschedule for another weekend. What have you been up to lately? How is running going?"
            },
            {
                "user_id": "032bbc38",
                "text": "Running is going fine. I am preparing for the marathon currently. This will be my first marathon so need to really prepare."
            },
            {
                "user_id": "63786412",
                "text": "What time are you setting for your goal?"
            },
            {
                "user_id": "032bbc38",
                "text": "As it's my first, anything below 4 hours I will be happy with. What animals did you go hunting for so far?"
            },
            {
                "user_id": "63786412",
                "text": "Mostly just deer. We have been trying to get an Elk tag, but no luck yet. Do you like deer meat?"
            },
            {
                "user_id": "032bbc38",
                "text": "Unfortunately I never had that in my life. But would love to try. How about you? Do you like it?"
            },
            {
                "user_id": "63786412",
                "text": "It makes good jerky, but not my favorite. What are you favorite meals?"
            },
            {
                "user_id": "032bbc38",
                "text": "I love meat, that's my favourite food. My wife likes chicken so it's mostly chicken in the house. My wife's recipe, thai chicken with rice is fantastic. What about you? What's your favourite food?"
            },
            {
                "user_id": "63786412",
                "text": "Yah, chicken is a staple with us as well. My favorite is jerk chick with red beans and rice. I'm also a big fan of mac n' cheese. How frequently do you cook?"
            },
            {
                "user_id": "032bbc38",
                "text": "I cook only during weekends, no energy left after work. But my wife cooks almost every day. You need to send me the recipe for jerk chicken."
            },
            {
                "user_id": "63786412",
                "text": "For sure, it's a great recipe and very easy. "
            },
            {
                "user_id": "032bbc38",
                "text": "I tried that jerk chicken recipe you sent me, it was very good! "
            },
            {
                "user_id": "63786412",
                "text": "Glad to hear! If youre running low on deer I can bring you some more. Also I'm planning to finally hunt for elk this weekend maybe I can bring some of that too."
            },
            {
                "user_id": "032bbc38",
                "text": "That sounds awesome, I do love to eat a lot of meat! Wife wants to try making jerk prime rib, which I think would be pure awesome"
            },
            {
                "user_id": "63786412",
                "text": "That sounds like heaven! Have you hit a new PR for running recently?"
            },
            {
                "user_id": "032bbc38",
                "text": "Not recently, I've had to take a pause on my running. I slipped and broke my ankle 5 days ago :("
            },
            {
                "user_id": "63786412",
                "text": "Oh no that's horrible how long do they think you'll be out for?"
            },
            {
                "user_id": "032bbc38",
                "text": "I was told 4-6 weeks to recover, but that's ok, I can get some whittling done without having to move around much. Carve up a few figurines :) "
            },
            {
                "user_id": "63786412",
                "text": "That's not too bad still unfortunate though. Perks of having multiple hobbies for sure!"
            },
            {
                "user_id": "032bbc38",
                "text": "Indeed! Wife said thank you for the mac and cheese too, she said it was better than hers!"
            },
            {
                "user_id": "63786412",
                "text": "She is so kind haha I can send the recipe over if she'd like."
            },
            {
                "user_id": "032bbc38",
                "text": "I'll let her know, she'll love it!"
            },
            {
                "user_id": "63786412",
                "text": "Great! Are you taking any time off work since you broke your ankle?"
            },
            {
                "user_id": "032bbc38",
                "text": "It's hard to get around the house with a broken ankle!"
            },
            {
                "user_id": "63786412",
                "text": "How long has it been broken? I broke my leg once a long time ago during the winter. It took forever to heal and the ice was a pain!"
            },
            {
                "user_id": "032bbc38",
                "text": "Almost a week! It hurts so bad! Really? How did you broke your leg?"
            },
            {
                "user_id": "63786412",
                "text": "I fell down the steps at church one icy Sunday. Thankfully it healed up but getting groceries by bus is a pain. "
            },
            {
                "user_id": "032bbc38",
                "text": "Oh! Well I think I´m going to the doctor tomorrow to see if my ankle is better "
            },
            {
                "user_id": "63786412",
                "text": "How badly did you break it? Usually they take a while to heal. "
            },
            {
                "user_id": "032bbc38",
                "text": "Basically my ankle is an smashed cookie right now. So yeah... it´s really bad"
            },
            {
                "user_id": "63786412",
                "text": "Did they think you were going to need surgery? I hope it heals ok for you. Are you planning any new whittling projects while you're laid up?"
            },
            {
                "user_id": "032bbc38",
                "text": "Yes! But my doctor wanted to wait a week until my ankle is okay for a surgery. Really no I´m not a good planner, what do you recommend me to do?"
            },
            {
                "user_id": "63786412",
                "text": "I haven't whittled in a while. The last thing I made was a plain wooden cross for my home. Do you have a favorite thing to make? I'm working on a set of raised planters for my garden."
            },
            {
                "user_id": "032bbc38",
                "text": "I love to make boats.  "
            },
            {
                "user_id": "63786412",
                "text": "Maybe you should start a model boat kit? I love to build things. I think that I usually make functional things. I always wanted to know how to build a full size sailboat by hand."
            }
        ]
