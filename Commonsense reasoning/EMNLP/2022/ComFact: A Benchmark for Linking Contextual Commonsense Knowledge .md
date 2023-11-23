# ComFact: A Benchmark for Linking Contextual Commonsense Knowledge 
Paper: https://aclanthology.org/2022.findings-emnlp.120.pdf
Repo:  https://github.com/Silin159/ComFact
Data:  https://drive.google.com/file/d/1h-9kK2ipoYiELqv6lOT6IarwlByGWuu1/view

## New terms


## Premise

## Problem
* Models trained with heuristically-retrieved commonsense knowledge learn simplified reasoning patterns (Wang et al, 2021), but provide false notion of interpretability (Raman et al, 2021).
* Inadequate knowledge retrieval from knowledge source is the root cause of wrong reasoning from a system. 
* So maybe if we retrieve more relevant commonsense knowledge, accurately, then it should yield better reasoning system. The challenges to retrieve more relevant commonsense knowledge are:
    * contextually relevant
    * should be able to handle implicit knowledge
    * should be able to handle ambiguity

## Results
* Learned fact linking models yields improvements of ~34.6% F1.
* Downstream improvements of 9.8%.
* Use Cohen's $k$ to measure relevance of fact candidates.
    * AR: always relevant
    * SR: sometimes relevant
    * AO: at odds
    * IRR: irrelevant

## Future works


## Sample data
``` json
{
    "text": [
        "hey , i am in a lady motorcycle club and i love to drive fast",
        "i am married to a wife beater and have two kids",
        "well do you want me to come beat him ? i have never lost a fight",
        "then we can go shopping ! i love shopping . i am a lifestyle shop blogger .",
        "well there you go lol and your kids would enjoy checking my tatts i have got 12",
        "i am very attractive . i was a cheerleader in high school . maybe we can go on a date",
        "u like women too ? did not know that",
        "got to get away from my husband i live in florida . celebration florida come meet me",
        "i just drove 20 mins this morning at 208 mph i can get there fast",
        "i will leave my kids never liked them lets do this !",
        "sounds like a plan i will be there soon you can hop on my bike",
        "the we can ride off into the sunset just like lovers in a novel",
        "well then pack your bags",
        "yay i am so excited i think i will burn the house down before i leave ."
        ],
        "facts": {
        "0": {
            "PersonX drives ___ fast": {
            "confidence": 1.0,
            "type": "pattern",
            "judges": [
                "relevant",
                "relevant"
            ],
            "triples": [
                {
                "relation": "isFilledBy",
                "tail": "motorcycles",
                "validation_1": {
                    "judges": [
                    "not",
                    "always"
                    ],
                    "overall": "at_odds"
                },
                "validation_2": {},
                "validation_3": {
                    "judges": [
                    "not",
                    "not"
                    ],
                    "overall": "not",
                    "secondary": "_"
                },
                "final": "not",
                "relationship": "irr",
                "final_judges": [
                    "not",
                    "not"
                ]
                },
                {
                "relation": "xIntent",
                "tail": "to ge there fast",
                "validation_1": {
                    "judges": [
                    "sometimes",
                    "not"
                    ],
                    "overall": "at_odds"
                },
                "validation_2": {},
                "validation_3": {
                    "judges": [
                    "not",
                    "not"
                    ],
                    "overall": "not",
                    "secondary": "_"
                },
                "final": "not",
                "relationship": "irr",
                "final_judges": [
                    "not",
                    "not"
                ]
                },
                {
                "relation": "xWant",
                "tail": "to race",
                "validation_1": {
                    "judges": [
                    "not",
                    "not"
                    ],
                    "overall": "not"
                },
                "validation_2": {},
                "validation_3": {},
                "final": "not",
                "relationship": "irr",
                "final_judges": [
                    "not",
                    "not"
                ]
                }
}
```

