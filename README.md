# FYP_Rally

NOTE: -	API key must be replaced yourself, create a secret key for your API key and replace the highlighted part “gemini_key = userdata.get('GeminiAPIKey')”. Applies for all 3 LLM with “userdata.get” 
OR you can directly put your API key in the highlighted part.

Open the Code in Colab
CODE NUMBER 1

Summary of how the code works:
Your initial prompt is run through gemini (base LLM) which gives a benchmark, the same prompt is send to the second LLM groq where it improves the prompt and sends it back to gemini to run for the second benchmark,
the initial prompt is then run through togetherAI where it improves the prompt and sends it back to gemini for the third benchmark. There will be 3 different responses from gemini running 3 different prompt, then you can compare which prompt is better.

Features: Colab Forms
review_text - your text to be evaluated
golden_prompt - the prompt used to evaluate review_text

consumer_qna - a qna profile to be evaluated 
consumer_profiling_prompt - the prompt used to evaluate "consumer_qna"

company_link - the website link to be extracted based off the prompt
business_profiling_prompt - the prompt used as the base to extract "company_link"

use_groq, use_together - toggles to select whether you want groq and/or together LLM to improve your initial prompt given.

There are 3 ways to use the code.
First - Response Evaluator: If you want to evaluate response based off a prompt, put your response in the text field "review_text" and your prompt in "golden_prompt". Gemini will then evaluate your response. If groq or toghether is toggled on, the prompt will be improved.

Second - Consumer Profiling: You evaulate a consumer profile through the input "consumer_qna" and "consumer_profiling_prompt". Gemini will then evaluate the response. If groq or together is toggled on, the prompt will be improved.

Third - Business Profiling: You extract information from the website through the input "company_link" based off your prompt in "business_profiling_prompt". If groq or together is toggled on, the prompt will be improved.

The responses will be logged into a google sheet which will be given in the output through a link.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CODE NUMBER 2
Summary of how the code works:
You input a consumer qna (your profile set) and 10 behavioural questions into the colab forms. The code will then call gemini to analyse your profile set and answer the 10 behavioural questions as if it were you. You can then judge its accuracy based on your own answers to the behavioural questions.

Features: Colab Forms
qna_profile - your profile set to be input for analysis
behavior_questions - the questions you want the LLM to answer.

The responses will be logged into a google sheet which will be given in the output through a link.
