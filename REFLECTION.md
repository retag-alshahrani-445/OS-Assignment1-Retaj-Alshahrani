# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

I learned that threads share memory and resources within a process, making them lightweight compared to separate processes. I also observed the thread lifecycle in practice: threads are created in the New state, become Runnable after the `start()` function is called, enter the Running state when executed by the processor, and finally terminate after the `run()` function completes its execution.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

The biggest challenge for me was calculating the waiting time for each operation, as I only succeeded after several attempts.The greatest difficulty lay in understanding the code and tracking the wait time throughout its various sections. Additionally, during my documentation, I encountered some difficulties with the English sentence structure.

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

I overcame the difficulties I faced in finding waiting time by reviewing the course syllabus, searching for similar examples online, watching YouTube videos, and finally, with the help of GPT chat, I was able to understand. As for the difficulties I encountered with writing in English, I overcame them by using Google Translate; I would write the text in Arabic and only double-check the terminology.

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

- In web browsers like Google Chrome, where each open tab or extension runs as a separate thread or process to prevent one crash from freezing the entire window.
- In high-end video games, multithreading is used to handle physics calculations on one thread while rendering graphics and processing user input on others, ensuring a smooth frame rate. 
- Also in live stream like TicTok, during a live stream, multiple threads are used at the same time: one thread handles video capture, another handles audio processing, another manages network transmission, and others handle user interactions like comments and likes. This ensures that the stream runs smoothly without delays or freezing.
---

## Additional Reflections (Optional)

### What would you like to learn more about?

---

### How confident do you feel about multithreading concepts now?

I rate myself as Intermediate. This is because I completed the assignment perfectly, but I encountered some difficulties in implementing the third feature. However, I feel I have a fairly good grasp of the material.

---

### Feedback on the assignment

Yes, I have some comments: the assignment was a bit long, but it was very useful and practical.

I suggest, for example, that the next assignment be based on the same concept but with only one additional feature instead of three, and that it be shorter.