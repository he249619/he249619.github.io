<!-- Load PyScript assets -->
<link rel="stylesheet" href="https://pyscript.net" />
<script type="module" src="https://pyscript.net"></script>

### Try My Python Script Live!
Type something below and watch Python process it in real-time.

<!-- HTML Input Element -->
<input type="text" id="user-input" placeholder="Type here..." style="padding: 5px; width: 200px;"/>
<button id="run-btn" style="padding: 5px 10px;">Run Python</button>

<div id="output-box" style="margin-top: 15px; font-weight: bold; color: green;"></div>

<!-- Your Python Script -->
<script type="py">
from pyscript import document

def process_data(event):
    # Grab the value from the HTML input box
    input_text = document.querySelector("#user-input").value
    
    # --- YOUR CUSTOM PYTHON LOGIC GOES HERE ---
    result = f"Python processed your input: {input_text.upper()} 🎉"
    # ------------------------------------------
    
    # Print the result back out to the HTML page
    document.querySelector("#output-box").innerText = result

# Bind the Python function to the button click
button = document.querySelector("#run-btn")
button.onclick = process_data
</script>
