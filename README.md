# AI_Assessment

This guide outlines the steps to set up and run the Retrieval Augmented Generation (RAG) system.

1. Load and preprocess the PDF document
Execute the code cell with the title "Load and preprocess the pdf document" (cell ID bfa946c6). This will extract text from the PDF, clean it, and print basic information.
2. Chunk the document
Execute the code cell with the title "Chunk the document" (cell ID 8457b411). This will split the cleaned text into smaller chunks with specified size and overlap.
3. Vectorize the chunks
Execute the code cell with the title "Vectorize the chunks" (cell ID ee6bcb46). This will load a Sentence Transformer model and generate embeddings for each chunk.
4. Create a Vector Database
Execute the code cell with the title "Create a Vector Database" (cell ID GVNkMsDFS0iI). This will create a FAISS vector store using the generated embeddings.
5. Implement the RAG System
Execute the code cell with the title "Implement the rag system" (cell ID c107b370). This defines the rag_query function using a pre-trained language model (Flan-T5 small). Note that the model loading might require specific libraries or handling depending on your environment and model availability.
Execute the subsequent code cell (cell ID XQ48m4K4TCu4) which attempts to load the text2text-generation pipeline for Flan-T5.
6. (Bonus) Implement a Conversation API
Execute the code cell defining the FastAPI app and QueryRequest model (cell ID f2574ac0).
Execute the code cell defining the /query endpoint (cell ID 3dc3b459).
Execute the code cell applying nest_asyncio (cell ID ewoDQEhUTPQj) to allow the API to run in a notebook environment.
To run the API: You will need to execute the uvicorn.run(app, host="0.0.0.0", port=3000) command. This is typically done in a separate cell or script, but in this notebook context, you would uncomment and run the uvicorn.run line within the cell where it's defined, or use nest_asyncio as applied in cell ewoDQEhUTPQj and then run cell 3dc3b459.
7. (Bonus) Implement RAG Evaluation
Execute the code cell defining the evaluate_rag_answer function (cell ID da7a030b). This provides a method to evaluate the quality of the generated answers.
8. (Bonus) Expose API with ngrok
Execute the code cell to install pyngrok (cell ID 3844740e).
Execute the code cell to authenticate ngrok and create a tunnel (cell ID 6866c34e). Remember to add your ngrok auth token to Colab secrets and replace the placeholder. This will provide a public URL to access your FastAPI.
9. (Bonus) Push to GitHub
Use the commands provided in the relevant code cells (e.g., cell ID b3bd4df1) to clone your repository, copy the notebook, commit changes, and push to GitHub. Remember to replace placeholder values and uncomment lines as needed.
After completing these steps, your RAG system should be set up, and you can test it by calling the rag_query function or interacting with the FastAPI endpoint if you set it up.
