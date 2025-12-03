import streamlit as st
import random

st.set_page_config(page_title="Catch the Treasure Game")

st.title("🏆 Catch the Treasure!")
st.write("Choose one of the three boxes. Only one has the treasure!")

# Initialize game state
if "treasure_box" not in st.session_state:
    st.session_state.treasure_box = random.randint(1, 3)

if "score" not in st.session_state:
    st.session_state.score = 0

# Display 3 buttons
col1, col2, col3 = st.columns(3)

with col1:
    if st.button("Box 1"):
        choice = 1
with col2:
    if st.button("Box 2"):
        choice = 2
with col3:
    if st.button("Box 3"):
        choice = 3

# Check result
if "last_choice" not in st.session_state:
    st.session_state.last_choice = None

if "choice" in locals():
    st.session_state.last_choice = choice
    if choice == st.session_state.treasure_box:
        st.success("🎉 You found the treasure!")
        st.session_state.score += 1
        st.session_state.treasure_box = random.randint(1, 3)  # reset for next round
    else:
        st.error("❌ No treasure here! Try again.")

# Score display
st.metric("Your Score", st.session_state.score)

# Reset game
if st.button("Restart Game"):
    st.session_state.treasure_box = random.randint(1, 3)
    st.session_state.score = 0
    st.session_state.last_choice = None
