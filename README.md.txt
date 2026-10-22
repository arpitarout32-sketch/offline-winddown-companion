## Code

```python
import streamlit as st
import ollama

st.set_page_config(
    page_title="Offline Wind-Down Companion",
    layout="centered"
)

st.title(":Sloth Mode: Offline Wind-Down Companion")
st.caption("100% Local :sparkles: Zero Internet Required :sparkles: Powered by Gemma 2")

st.write(
    "Disconnect from the noise. Enter two soothing themes below "
    "to generate a local, calming bedtime story and ambient audio recipe."
)

col1, col2 = st.columns(2)
with col1:
    word1 = st.text_input("First Cozy Theme:", value="Rain on a tin roof")
with col2:
    word2 = st.text_input("Second Cozy Theme:", value="Warm tea")

if st.button("Generate Wind-Down Story :sparkles:", use_container_width=True):
    if not word1.strip() or not word2.strip():
        st.warning("Please enter two themes to guide your story.")
    else:
        with st.spinner("Crafting your story completely offline..."):
            prompt = f"""
            You are a gentle and soothing bedtime storyteller. 
            Write a very short, ultra-relaxing 3-paragraph bedtime story incorporating these two themes: '{word1}' and '{word2}'. 
            Use slow, atmospheric, and calming imagery.
            At the end, provide a section titled 'Ambient Soundscape Recipe' that lists 3 cozy background sounds to play along with this story.
            """
            
            try:
                response = ollama.chat(
                    model='gemma2:2b',
                    messages=[{'role': 'user', 'content': prompt}]
                )
                
                st.markdown("---")
                st.markdown("Your Bedtime Story")
                st.write(response['message']['content'])
                st.success("Generated 100% locally on your machine.")
                
            except Exception as e:
                st.error(f"Could not connect to Ollama. Make sure Ollama is running: {e}")
```