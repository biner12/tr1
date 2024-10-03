import streamlit as st
from PIL import Image

img = Image.open("solved problem.jpg")
st.image(
    img,
    caption = 'Diff' ,
    width = 800 ,
    channels = "RGB"
)
