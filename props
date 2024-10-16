from fastapi import FastAPI, Form
from fastapi.responses import HTMLResponse

app = FastAPI()

@app.get("/", response_class=HTMLResponse)
async def get_form():
    return """
    <html>
        <head>
            <title>Job Proposal Generator</title>
        </head>
        <body>
            <h1>Job Proposal Generator</h1>
            <form action="/generate_proposal" method="post">
                <label>Job Title:</label><br>
                <input type="text" name="job_title" required><br><br>
                
                <label>Company Name:</label><br>
                <input type="text" name="company_name" required><br><br>
                
                <label>Job Description:</label><br>
                <textarea name="job_description" required></textarea><br><br>
                
                <label>Your Name:</label><br>
                <input type="text" name="your_name" required><br><br>
                
                <label>Your Contact:</label><br>
                <input type="text" name="your_contact" required><br><br>
                
                <button type="submit">Generate Proposal</button>
            </form>
        </body>
    </html>
    """

@app.post("/generate_proposal")
async def generate_proposal(
    job_title: str = Form(...),
    company_name: str = Form(...),
    job_description: str = Form(...),
    your_name: str = Form(...),
    your_contact: str = Form(...)):
    
    # Here, you can implement your proposal generation logic
    proposal_response = f"Generated proposal for **{job_title}** at **{company_name}**.\n\nDescription: {job_description}\n\nPrepared by: **{your_name}**\nContact: **{your_contact}**"
    
    return {"response": proposal_response}

# To run the server, use the command:
# uvicorn proposal:app --reload
