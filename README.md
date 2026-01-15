# Day 2 -> RAG Systems (Retrieval-Augmented Generation)

- Thanks to @https://github.com/Jaskirat-singh04 for the session on RAG systems and the hands on coding for the Winter School Python with Gen AI_Day-2_Rag-agent Colab notebook.

## RAG is a framework and not an architecutre

- Framework that combines the question and the relevant chunks to obtain the answer.
- The asked question by the user is checked by retriever that retrieves that fixed data from the knowledge base (which is separated and broken down into chunks and embedded into numerical values, each numerical value of a word is mapped to the word itself, which finally passes the word chunks) to the LLM instead of the complete knowledge base at once. Only the relevant chunk of the knowledge base is passed (Context Window Problem - fixed LLM memory causes LLM's to forget crucial details in long chats/conversations leading to errors, hallucinations, and decreased accuracy)
- There is a slight overlapping between chunks to build a better connection between them and the selected chunk provides slight context about its previous and next chunks.
- In the retriever, the number of chunks to retrieve is determined by the top-k parameter, a value that is set by the system designer, not determined automatically by the system itself. A small k risks missing crucial info, while a large k adds computational cost and noise.
- User query, relevant chunks, system instruction are the 3 most important parts of the context builder (prompt assembly).
- RAG's take multiple types of data - text, images (text extracted by OCR), videos (text extracted from audio transcripts) and many other types of data.

## Notion document - https://www.notion.so/RAG-Pipeline-with-LangChain-Google-Gemini-and-Agents-2e514dc3f1ec8051835cfb236da43fa9

## Colab Notebook Copy created and added to drive

# Day 3 -> AI Agents and Automation

- Thanks to @https://github.com/Tush-hub for the session on AI agents and Automation and the hands on coding session.

## Basics of AI Infrastructure -

- GPU (Graphic Processing Unit) is a specialized processor designed for parallel processing (Key task in AI). It is excellent for tasks that require massive data calculations.
- TPU's (Tensor Processing Unit) AND NPU's (Neural Processing Unit) exist beyond GPU's offering even higher computation power.

## How AI thinks -

- Tokens - Breaking down the key query/sentence into key words that are tokens, excluding words like is/and/are/or etc.
- Embeddings - The created tokens are converted into high-dimensional vectors (list of numbers)
- Self-Attention - The model weighs the importance of all other tokens in the context of each new token it predicts
- Probability - The model calculates the most probable next token in the answer sentence that the AI returns.

## Art of Prompt Writing

- Include details like persona, task, context and a proper format.
- Types of prompts include -
  - Zero-Shot - Ask directly.
  - Few-Shot - Provide some examples.
  - Structured - Define output format (mostly done in JSON), forcing the AI to be precise.

### We can create AI songs on suno.ai

## Threats to AI Agents

- Prompt Injection - Replacing key information of the prompt with personal information that sends data to others or causes tool to misbehave.
- Tool Misuse - Misuse of the created tool by users to create content that might be offensive or obscene.
- Data Leakage - Data getting leaked from the tool causing users to lose crucial personal information.
- Unauthorized Actions - The tool performs actions that it is not meant to do or authorized to do, saying or doing the wrong stuff.

### AI Agents are hence more riskier than normal chatbot agents as they can act and trigger systems that cause a real-world impact.

### Guardrails must be designed to control tool behaviour by permission scoping and auditing tool outputs.

## Apps that we built in the Google AI Studio ->

### Celestial Hands: 3D Particle Interaction

- Prompt given in Google AI Studio -

- Create a real time interaction 3D particle system with Three.js
- Requirements: -

  - Detect both hands through the camera -> control particle scaling + expansion by hand tension and closing
  - Include a panel to switch templates: hearts/flowers/saturn/fireworks
  - Add a color selector to change the particle colors
  - Particles must react instantly to gesture changes
  - UI should be simple, modern and clean.

- The created app with all details present on Google Drive and Google AI Studio.

### Conversational AI app for any task (E-Commerce App in this case)

- Prompt given in Google AI Studio -

- Create a conversational voice app for an ecommerce store which takes the order information from the customer and checks the order in the inventory an responds back. It should be multi-lingual an support majority of the Indian languages

- The created app with all details present on Google Drive and Google AI Studio.

## Along with building these apps we also learnt a lot of tools that exist and how they can be used.

## We also tried generating professional-grade images with a specific output using JSON schemas in Google's Gemini Nano Banana Pro. The prompt used was as follows: -

- JSON Schema -

```json
{
  "task": "image_generation",
  "model": "gemini-nano-banana",
  "input": {
    "reference_images": {
      "front_face": "USER_PROVIDED_IMAGE_FRONT",
      "left_profile": "USER_PROVIDED_IMAGE_LEFT",
      "right_profile": "USER_PROVIDED_IMAGE_RIGHT"
    },
    "prompt": {
      "description": "Create a hyper-realistic professional LinkedIn visual portrait using the provided reference images. Preserve 100% of the subject’s real facial attributes with absolute identity consistency.",
      "identity_preservation": {
        "face_structure": "exact",
        "skin_tone": "exact",
        "facial_symmetry": "exact",
        "eye_shape_color_position": "exact",
        "nose_shape_bridge_width": "exact",
        "lip_shape_volume": "exact",
        "jawline_chin": "exact",
        "ear_shape_position": "exact",
        "hairline_density_texture": "exact",
        "age": "unchanged",
        "gender_features": "unchanged",
        "no_face_morphing": true,
        "no_ai_face_averaging": true
      },
      "pose_and_expression": {
        "head_position": "slight professional angle",
        "eye_direction": "looking directly at the camera",
        "expression": "confident, calm, approachable",
        "mouth": "natural subtle smile"
      },
      "attire_and_grooming": {
        "outfit": "tailored dark navy or charcoal professional suit",
        "shirt": "crisp white formal shirt",
        "tie": "minimalist solid-color tie",
        "fit": "executive-level, well-fitted",
        "grooming": "clean, professional, natural"
      },
      "lighting_and_camera": {
        "lighting": "soft studio lighting, even facial illumination, no harsh shadows",
        "camera": "85mm portrait lens look",
        "depth_of_field": "shallow background blur (bokeh)",
        "resolution": "ultra-high resolution",
        "sharpness": "high facial detail, natural skin texture"
      },
      "background": {
        "type": "neutral professional",
        "style": "soft gradient or modern corporate backdrop",
        "distraction_free": true
      },
      "quality_constraints": {
        "photorealism": "maximum",
        "skin_texture": "natural pores, no over-smoothing",
        "no_cartoon_effect": true,
        "no_art_style": true,
        "no_unreal_features": true,
        "linkedin_ready": true
      },
      "final_output": {
        "framing": "head and shoulders",
        "aspect_ratio": "1:1",
        "use_case": "LinkedIn profile picture",
        "professional_score": "very high",
        "confidence_level": "executive presence"
      }
    }
  }
}
```
