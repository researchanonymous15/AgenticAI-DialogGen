<h1 align="center">  
AgenticAI-DialogGen: Topic-guided Conversation Generation for Fine-tuning and Evaluating Short- and Long-term Memory of LLMs
</h1>  


## **TopicGuidedChat (TGC) Dataset — Sample Release**

This repository contains a sample version of the TopicGuidedChat (TGC) dataset generated via the AgenticAI-DialogGen framework described in our paper* entitled, “AgenticAI-DialogGen: Topic-guided Conversation Generation for Fine-tuning and Evaluating Long-term Memory of LLMs”. The TGC dataset is a large-scale synthetic benchmark derived from the [Multi-Session Chat (MSC) dataset](https://aclanthology.org/2022.acl-long.356/) and is designed to support research on fine-tuning and evaluating the long-term memory of LLMs.

## **Publication Status**

_This paper* has been submitted to ACL 2026 and is currently under review. This repository provides only a sample to illustrate the dataset schema and content. The complete version of the dataset will be released after the paper review process._


## **About the TGC Dataset**

Conversations are organized by topics, thereby enabling precise modeling of topic coherence and memory grounding.

For each speaker pair, the dataset includes:
-  Up to 3 topics.
-  AVG 30 conversational turns for each topic as short-term memory.
-  Speaker-specific knowledge graphs as long-term memory derived from MSC dataset conversations.
-  20 Memory-grounded QA pairs per topic probing both short- and long-term memory.

At full scale, the dataset comprises:
- 1,001 persona profiles.
- 4,004 conversations totaling 89,550 conversational turns.
- 2,985 topic instances across conversations.
- 146,237 speaker-wise knowledge graphs.
- 59,700 QA pairs for memory evaluation.

## 🤖 **About the AgenticAI-DialogGen Framework**

AgenticAI-DialogGen is a modular agent-based framework for generating topic-guided and persona grounded conversations without human annotation. The framework extracts knowledge from the MSC dataset, organizes it into coherent topics, and constructs speaker-specific knowledge graphs. Leveraging LLM agents, it simulates realistic multi-turn conversations which are then validated, refined, and enriched with memory-grounded QA pairs to support both short- and long-term memory evaluation.

## 📂 Sample of the TGC Dataset

Below is a snippet showing the dataset structure for a **single topic** with **speaker-wise knowledge graphs** and **newly generated conversational turns**.

```json

     "conversations": [
    {
      "topic": "Food Preferences",
      "participants": [
        "speaker1",
        "speaker2"
      ],
      "personas": [
        {
          "name": "speaker1",
          "background_facts": [
            {
              "subject": "speaker1",
              "relation": "eats exclusively",
              "object": "meat",
              "source_turn": 6,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1",
              "relation": "favorite meat",
              "object": "prime rib",
              "source_turn": 8,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1",
              "relation": "has never tried",
              "object": "deer meat",
              "source_turn": 20,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1",
              "relation": "loves",
              "object": "meat",
              "source_turn": 22,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1",
              "relation": "tried",
              "object": "jerk chicken recipe",
              "source_turn": 26,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1's wife",
              "relation": "likes",
              "object": "chicken",
              "source_turn": 22,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1's wife",
              "relation": "makes",
              "object": "thai chicken with rice",
              "source_turn": 22,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker1's wife",
              "relation": "wants to try",
              "object": "making jerk prime rib",
              "source_turn": 28,
              "type": "knowledge_triple"
            },
           { 
              "subject": "speaker1's wife",
              "relation": "cooks",
              "object": "almost every day",
              "source_turn": 24,
              "type": "knowledge_triple"
            },
           { 
              "subject": "speaker1",
              "relation": "cooks",
              "object": "only on weekends",
              "source_turn": 24,
              "type": "knowledge_triple"
            }
          ],
          "personality_traits": [
            "carnivorous",
            "adventurous eater",
            "supportive partner"
          ],
          "topics_of_interest": [
            "prime rib recipes",
            "exploring new meat dishes",
            "supporting spouse's culinary experiments"
          ]
        },
        {
          "name": "speaker2",
          "background_facts": [
            {
              "subject": "speaker2",
              "relation": "likes",
              "object": "chicken",
              "source_turn": 9,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker2",
              "relation": "likes",
              "object": "chicken or macaroni and cheese",
              "source_turn": 9,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker2",
              "relation": "favorite is",
              "object": "jerk chicken with red beans and rice",
              "source_turn": 23,
              "type": "knowledge_triple"
            },
            {
              "subject": "speaker2",
              "relation": "says",
              "object": "deer meat makes good jerky",
              "source_turn": 21,
              "type": "knowledge_triple"
            }
          ],
          "personality_traits": [
            "food enthusiast",
            "adventurous eater",
            "comfort food lover"
          ],
          "topics_of_interest": [
            "jerk chicken recipes",
            "comfort food dishes",
            "culinary pairings"
          ]
        }
      ],
      "turns": [
        {
          "speaker": "speaker1",
          "text": "I love talking about meat! What's your favorite type of meat to eat?",
          "turn_number": 1
        },
        {
          "speaker": "speaker2",
          "text": "I really enjoy chicken, especially jerk chicken with red beans and rice. How about you?",
          "turn_number": 2
        },
        {
          "speaker": "speaker1",
          "text": "I love prime rib, but I recently tried a jerk chicken recipe too. It was pretty tasty!",
          "turn_number": 3
        },
        {
          "speaker": "speaker2",
          "text": "Jerk chicken is such a flavorful dish! Did you make it spicy or keep it mild?",
          "turn_number": 4
        },
        {
          "speaker": "speaker1",
          "text": "I went for a bit of spice to give it a kick. My wife loves chicken, so she enjoyed it too!",
          "turn_number": 5
        },
        {
          "speaker": "speaker2",
          "text": "That's awesome! Adding some spice really brings out the flavors. Have you tried pairing it with any sides?",
          "turn_number": 6
        },
        {
          "speaker": "speaker1",
          "text": "I haven't tried pairing it with sides yet, but my wife makes a great Thai chicken with rice. Maybe I'll try that next time!",
          "turn_number": 7
        },
        {
          "speaker": "speaker2",
          "text": "Thai chicken with rice sounds delicious! You could also try pairing jerk chicken with some mac n' cheese for a comforting twist.",
          "turn_number": 8
        },
        {
          "speaker": "speaker1",
          "text": "That sounds like a great idea! I bet the creamy mac n' cheese would balance the spice nicely.",
          "turn_number": 9
        },
        {
          "speaker": "speaker2",
          "text": "Absolutely! The creaminess of mac n' cheese complements the spice perfectly. It's a match made in comfort food heaven!",
          "turn_number": 10
        },
        {
          "speaker": "speaker1",
          "text": "I might just have to give that a try next time. My wife also wants to experiment with making jerk prime rib, which sounds exciting!",
          "turn_number": 11
        },
        {
          "speaker": "speaker2",
          "text": "Jerk prime rib sounds like an adventurous twist! I'm sure it'll be packed with flavor.",
          "turn_number": 12
        },
        {
          "speaker": "speaker1",
          "text": "I'm really looking forward to it. I think the spices will work great with the richness of prime rib.",
          "turn_number": 13
        },
        {
          "speaker": "speaker2",
          "text": "That sounds like a delicious experiment! Let me know how it turns out with the prime rib.",
          "turn_number": 14
        },
        {
          "speaker": "speaker1",
          "text": "I'll definitely keep you posted on how it goes. I'm excited to see how the flavors come together!",
          "turn_number": 15
        },
        {
          "speaker": "speaker2",
          "text": "Can't wait to hear about it! Trying new flavor combinations is always exciting.",
          "turn_number": 16
        },
        {
          "speaker": "speaker1",
          "text": "I usually only cook on weekends, so when I get the chance, I like trying something a bit special with meat.",
          "turn_number": 17
        },
        {
          "speaker": "speaker2",
          "text": "It sure will be! Cooking is all about exploring and enjoying new tastes.",
          "turn_number": 18
        },
        {
          "speaker": "speaker1",
          "text": "Since I eat meat almost exclusively, I never get bored of finding new ways to prepare it.",
          "turn_number": 19
        },
        {
          "speaker": "speaker2",
          "text": "There's always a new twist to try with meat dishes. Have you ever thought about adding a unique sauce or marinade to your experiments?",
          "turn_number": 20
        },
        {
          "speaker": "speaker1",
          "text": "I haven't thought about a unique sauce yet, but that sounds like a fun idea. Maybe a tangy marinade could add an interesting layer to the prime rib.",
          "turn_number": 21
        },
        {
          "speaker": "speaker2",
          "text": "A tangy marinade could definitely add a nice zing to the prime rib. Citrus or vinegar-based marinades might work well for that extra kick.",
          "turn_number": 22
        },
        {
          "speaker": "speaker1",
          "text": "I'll have to look into some citrus-based marinades. They could really enhance the flavors of the prime rib.",
          "turn_number": 23
        },
        {
          "speaker": "speaker2",
          "text": "Citrus marinades can really brighten up the dish. Let me know if you find a good recipe!",
          "turn_number": 24
        },
        {
          "speaker": "speaker1",
          "text": "I'll definitely share if I find a great one. I'm excited to see how the citrus pairs with the richness of the meat!",
          "turn_number": 25
        },
        {
          "speaker": "speaker2",
          "text": "I'm sure it'll be a fantastic combination! Citrus and rich meats often create a delightful balance.",
          "turn_number": 26
        },
        {
          "speaker": "speaker1",
          "text": "My wife cooks almost every day, so she's usually the one leading these experiments while I help out.",
          "turn_number": 27
        },
        {
          "speaker": "speaker2",
          "text": "It sounds like a tasty adventure indeed! Enjoy the process, and I'm sure it'll turn out amazing.",
          "turn_number": 28
        },
        {
          "speaker": "speaker1",
          "text": "If it turns out well, I might even share some with you, especially if you bring over any meat from your hunts.",
          "turn_number": 29
        },
        {
          "speaker": "speaker2",
          "text": "Looking forward to hearing all about it! Enjoy the cooking and the delicious results.",
          "turn_number": 30
        }
      ],

      "qa_pairs": [
        {
          "question_id": 1,
          "question": "Do I eat exclusively meat?",
          "answer": "Yes"
        },
        {
          "question_id": 2,
          "question": "What is my favorite type of meat?",
          "answer": "Prime rib"
        },
        {
          "question_id": 3,
          "question": "Have I ever tried deer meat?",
          "answer": "No"
        },
        {
          "question_id": 4,
          "question": "What recipe did I recently try?",
          "answer": "Jerk chicken"
        },
        {
          "question_id": 5,
          "question": "Does my wife like chicken?",
          "answer": "Yes"
        },
        {
          "question_id": 6,
          "question": "What recipe does my wife make with rice?",
          "answer": "Thai chicken"
        },
        {
          "question_id": 7,
          "question": "How often does my wife usually cook?",
          "answer": "Almost every day"
        },
        {
          "question_id": 8,
          "question": "What type of prime rib does my wife want to try making?",
          "answer": "Jerk prime rib"
        },
        {
          "question_id": 9,
          "question": "Did I make the jerk chicken spicy?",
          "answer": "Yes"
        },
        {
          "question_id": 10,
          "question": "What side dish was suggested to pair with jerk chicken?",
          "answer": "Mac n' cheese"
        },
        {
          "question_id": 11,
          "question": "Am I excited to try jerk prime rib?",
          "answer": "Yes"
        },
        {
          "question_id": 12,
          "question": "What kind of marinade was suggested for prime rib?",
          "answer": "Citrus-based"
        },
        {
          "question_id": 13,
          "question": "Did I plan to try citrus marinades?",
          "answer": "Yes"
        },
        {
          "question_id": 14,
          "question": "What does my wife enjoy making with chicken?",
          "answer": "Thai chicken"
        },
        {
          "question_id": 15,
          "question": "Have I tried pairing jerk chicken with sides?",
          "answer": "No"
        },
        {
          "question_id": 16,
          "question": "What did I think would balance the spice of jerk chicken?",
          "answer": "Mac n' cheese"
        },
        {
          "question_id": 17,
          "question": "Am I looking forward to experimenting with flavors?",
          "answer": "Yes"
        },
        {
          "question_id": 18,
          "question": "What did I recently try that was tasty?",
          "answer": "Jerk chicken"
        },
        {
          "question_id": 19,
          "question": "Do I love talking about meat?",
          "answer": "Yes"
        },
        {
          "question_id": 20,
          "question": "Do I cook on weekdays?",
          "answer":  "No"
        }

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

