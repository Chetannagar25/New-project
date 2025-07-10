# New-project
form to apply for job 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Apply to Project</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f8;
    }

    .container {
      max-width: 600px;
      margin: 50px auto;
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
      color: #333;
    }

    label {
      font-weight: bold;
      margin-top: 15px;
      display: block;
    }

    input, select, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    button {
      margin-top: 20px;
      width: 100%;
      padding: 12px;
      background-color: #28a745;
      color: white;
      font-size: 16px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #218838;
    }

    .success-message {
      text-align: center;
      margin-top: 15px;
      color: green;
      display: none;
    }
  </style>
</head>
<body>

<div class="container">
  <h2>Apply for the Project</h2>
  <form id="applicationForm" action="https://formspree.io/f/xdkzqowo" method="POST">
    <!-- Replace the action URL with your own Formspree endpoint -->

    <label for="name">Full Name:</label>
    <input type="text" name="Name" required />

    <label for="email">Email Address:</label>
    <input type="email" name="Email" required />

    <label for="phone">Phone Number:</label>
    <input type="tel" name="Phone" required pattern="[0-9]{10}" />

    <label for="skills">Your Skills:</label>
    <input type="text" id="skills" name="skills" placeholder="e.g. Web Dev, Python, Design, Other... " required />

    <label for="role">Preferred Role:</label>
    <select name="Role" required>
      <option value="">-- Select --</option>
      <option value="frontend">Frontend Developer</option>
      <option value="backend">Backend Developer</option>
      <option value="designer">UI/UX Designer</option>
      <option value="tester">Tester</option>
      <option value="manager">Project Manager</option>
        <option value="other">Other</option>
    </select>
    <label for="resumeLink">Resume Link (Google Drive, Dropbox, etc.):</label>
    <input type="url" name="Resume Link" placeholder="https://drive.google.com/..." required />

    <label for="availability">Availability (Hours Per Day):</label>
    <input type="number" name="Availability" min="1" max="24" required />
    <label for="experience">Years of Experience:</label>
    <input type="number" name="Experience" min="0" max="50" required />

    <label for="why">Why should we select you?</label>
    <textarea name="Why" rows="4" required></textarea>

    <!-- Optional: Honeypot (spam protection) -->

    <input type="text" name="_honey" style="display:none">
    <input type="hidden" name="_subject" value="New Project Application" optional />
    <input type="hidden" name="_captcha" value="false" />

    <!-- Optional: Redirect after success -->
    <input type="hidden" name="_next" value="thankyou.html" />
    <!-- Replace with your thank you page URL -->


    <button type="submit">Submit</button>
    <div class="success-message" id="successMessage">Thanks! Your application was sent.</div>
  </form>
</div>

<script>
  document.getElementById("applicationForm").addEventListener("submit", function(event) {
    document.getElementById("successMessage").style.display = "block";
  });
</script>

</body>
</html>
