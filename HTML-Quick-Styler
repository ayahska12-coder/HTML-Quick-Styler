import gradio as gr
from transformers import pipeline

generator = pipeline("text-generation", model="ibm-granite/granite-3.3-2b-instruct")

def generate_page(title, description, color):
    
    html = f"""
    <html>
    <head>
    <title>{title}</title>
    <style>
    body{{font-family:Arial;background:#111;color:white;padding:20px}}
    h1{{color:#4f46e5}}
    section{{margin-top:20px}}
    button{{background:#4f46e5;color:white;padding:10px;border:none}}
    </style>
    </head>

    <body>
    <h1>{title}</h1>

    <section>
    <p>{description}</p>
    </section>

    <section>
    <h2>Features</h2>
    <ul>
    <li>Responsive design</li>
    <li>Modern UI</li>
    <li>AI generated page</li>
    </ul>
    </section>

    <section>
    <h2>Contact</h2>
    <button>Contact Us</button>
    </section>

    </body>
    </html>
    """

    return html


interface = gr.Interface(
    fn=generate_page,
    inputs=[
        gr.Textbox(label="Page Title"),
        gr.Textbox(label="Page Description"),
        gr.Dropdown(["modern","creative","minimal"], label="Color Style")
    ],
    outputs=gr.Code(language="html"),
    title="HTML Quick Styler"
)

interface.launch(share=True)
