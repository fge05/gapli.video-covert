<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Video and Image Compression Tool with dynamic functionality and monetization via Google AdSense.">
    <meta name="keywords" content="Video compression, Image optimization, GIPLI, dynamic functionality, SEO, AdSense">
    <title>Video & Image Compression Tool</title>
    
    <!-- SEO and social media meta tags -->
    <meta property="og:title" content="Video & Image Compression Tool">
    <meta property="og:description" content="Optimize and compress your video and images with ease using our dynamic tool.">
    <meta property="og:image" content="your-image.jpg">
    
    <style>
        /* General Layout */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        header {
            background-color: #333;
            padding: 10px 0;
        }

        nav ul {
            list-style-type: none;
            text-align: center;
        }

        nav ul li {
            display: inline;
            margin-right: 20px;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
        }

        /* Main content styling */
        .container {
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-size: 2.5rem;
        }

        .compression-tool {
            margin-top: 20px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .compression-tool {
                width: 90%;
                margin: 0 auto;
            }
        }

        /* Advertisement Container */
        .ad-container {
            margin-top: 30px;
        }

        /* Footer styling */
        footer {
            text-align: center;
            background-color: #333;
            color: white;
            padding: 10px;
        }
    </style>
</head>
<body>
    <!-- Navigation Bar (Optional) -->
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Main Content Section -->
    <section id="home">
        <div class="container">
            <h1>Welcome to Our Video & Image Compression Tool</h1>
            <p>Optimize your video and image files with adjustable compression levels.</p>
            
            <!-- Image/Video Compression Tool -->
            <div class="compression-tool">
                <input type="file" id="fileUpload" accept="image/*,video/*" />
                <label for="compressionLevel">Choose Compression Level:</label>
                <select id="compressionLevel">
                    <option value="low">Low</option>
                    <option value="medium">Medium</option>
                    <option value="high">High</option>
                </select>
                <button onclick="compressFile()">Compress</button>
                
                <div id="output"></div>
            </div>
        </div>
    </section>

    <!-- Advertisements Section -->
    <section id="ads">
        <div class="ad-container">
            <!-- Google AdSense Code (Insert Ad Unit ID here) -->
            <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
            <ins class="adsbygoogle"
                style="display:block"
                data-ad-client="ca-pub-XXXXXXX"
                data-ad-slot="XXXXXXX"
                data-ad-format="auto"></ins>
            <script>
                (adsbygoogle = window.adsbygoogle || []).push({});
            </script>
        </div>
    </section>

    <!-- Footer Section -->
    <footer>
        <p>&copy; 2025 Video & Image Compression Tool</p>
    </footer>

    <script>
        // Function to compress images/videos based on selected compression level
        function compressFile() {
            let file = document.getElementById("fileUpload").files[0];
            let compressionLevel = document.getElementById("compressionLevel").value;
            let outputDiv = document.getElementById("output");

            if (file) {
                // Simulating compression based on level selected
                let reader = new FileReader();
                reader.onload = function(event) {
                    let fileType = file.type.startsWith('image') ? 'image' : 'video';
                    let outputHtml = `<h3>Compressed ${fileType}</h3><p>Compression Level: ${compressionLevel}</p>`;
                    outputDiv.innerHTML = outputHtml + `<img src="${event.target.result}" alt="Compressed File" />`;
                };

                reader.readAsDataURL(file);
            } else {
                outputDiv.innerHTML = "<p>Please select a file to compress.</p>";
            }
        }
    </script>
</body>
</html>
