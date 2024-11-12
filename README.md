# medical-bot
Medical chatbot using Gen AI


##### Data: HealthyHeart Pdf
    https://www.nhlbi.nih.gov/files/docs/public/heart/healthyheart.pdf
        
Frameworks:

    Lagchain - Pipeline
    Llama - LLM Model
        BioMistral-7B
        https://huggingface.co/MaziyarPanahi/BioMistral-7B-GGUF/tree/main
    Sentence transformers - Embedding Model
       PubMedBert - Base - embeddings   (language model for generating the embeddings)
       https://huggingface.co/NeuML/pubmedbert-base-embeddings
    Chroma - Vector Store
    
Langchain framework for building a pipeline end to end (just line pytorch and tesorflow)
Llama for loading LLM OSS model
Chroma is a database we gonna use

#### Process -

indexing :
   1. Load the doc and parse the text
   2. Divide text into chunks - chunking
   3. create embedding vectors for each chunk
   4. store chunks and embeddings to vector store
    
    
Querying: 
        
        Load LLM model
        
        Build Application chain end to end
        
        Query the chatbot :
        
            1. Pass query to retriever
            2. Retrieves relevant docs from vector store (KNN)
            3. Pass both and docs to LLM
            4. Generate the response
