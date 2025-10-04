<html>
<body>
<!--StartFragment--><html><head></head><body><p>Here’s the same <strong>GitHub Pull Request description</strong>, but without emojis — clean and professional for technical submissions:</p>
<hr>
<h3>Metro Platform Monitoring Tool — YOLO + HOG Person Detection, Tracking, and Safety Analytics</h3>
<h4>What This PR Adds</h4>
<p>This pull request introduces a real-time metro platform monitoring system built with Python, OpenCV, and YOLOv8.<br>
The tool provides a lightweight, extendable baseline for crowd monitoring, intrusion detection, and density analysis — ideal for Hacktoberfest or smart city safety projects.</p>
<hr>
<h3>Core Features</h3>
<ol>
<li>
<p><strong>Continuous Video Monitoring</strong></p>
<ul>
<li>
<p>Reads video input from file or live webcam feed.</p>
</li>
<li>
<p>Detects people using YOLOv8n (preferred) or HOG pedestrian detector as fallback.</p>
</li>
<li>
<p>Tracks movement frame-to-frame using a centroid-based tracking algorithm.</p>
</li>
</ul>
</li>
<li>
<p><strong>Intrusion Detection (Safety Line)</strong></p>
<ul>
<li>
<p>Calibrate a safety line by pressing <code inline="">l</code> and clicking along the platform edge.</p>
</li>
<li>
<p>Once finalized with <code inline="">ENTER</code>, any person crossing below this line triggers an intrusion alert.</p>
</li>
<li>
<p>Reset anytime with <code inline="">r</code>.</p>
</li>
<li>
<p>Easily adaptable for reversed camera angles or different intrusion logic.</p>
</li>
</ul>
</li>
<li>
<p><strong>Crowd Density Estimation</strong></p>
<ul>
<li>
<p>Calculates real-time crowd density within predefined polygon zones (e.g., the platform).</p>
</li>
<li>
<p>Displays alerts when density exceeds threshold (default: <code inline="">0.00025</code>).</p>
</li>
<li>
<p>Add custom zones like:</p>
<pre><code class="language-python">self.zones.append(("PLATFORM", platform, 0.00025))
self.zones.append(("GATE", [(x1,y1),(x2,y2),(x3,y3),(x4,y4)], 0.00030))
</code></pre>
</li>
</ul>
</li>
<li>
<p><strong>Lightweight Tracking Logic</strong></p>
<ul>
<li>
<p>Associates detections by comparing centroid distances (&lt; 200² threshold).</p>
</li>
<li>
<p>Automatically removes inactive tracks after 2 seconds.</p>
</li>
<li>
<p>Prevents duplicate intrusion alerts for the same person.</p>
</li>
</ul>
</li>
<li>
<p><strong>YOLO vs HOG Toggle</strong></p>
<ul>
<li>
<p>Switch between YOLO (accuracy) and HOG (speed) dynamically using the <code inline="">y</code> key.</p>
</li>
<li>
<p>If YOLO fails to load, install it via:</p>
<pre><code class="language-bash">pip install ultralytics
</code></pre>
</li>
</ul>
</li>
</ol>
<hr>
<h3>Runtime Controls</h3>

Key | Action
-- | --
q | Quit
p | Pause / Resume
y | Toggle YOLO
l | Start / Stop safety line calibration
ENTER | Finalize safety line
r | Reset safety line
z | Toggle zone polygon drawing
d | Toggle density alerts
c | Toggle track ID display
Left Click | Add calibration point
Right Click | Undo last point


<hr>
<h3>Run Instructions</h3>
<p><strong>Video file:</strong></p>
<pre><code class="language-bash">python metro_platform_monitor\metro_monitor.py --video "C:\Path\to\your_video.mp4"
</code></pre>
<p><strong>Webcam (index 0):</strong></p>
<pre><code class="language-bash">python metro_platform_monitor\metro_monitor.py --camera 0
</code></pre>
<p><strong>Force HOG only (skip YOLO):</strong></p>
<pre><code class="language-bash">python metro_platform_monitor\metro_monitor.py --video "video.mp4" --no-yolo
</code></pre>
<hr>
<h3>Installation</h3>
<p>From the project root, install dependencies:</p>
<pre><code class="language-bash">pip install -r requirements.txt
</code></pre>
<p>(If YOLO isn’t needed, skip <code inline="">ultralytics</code> and run with <code inline="">--no-yolo</code>.)</p>
<hr>
<h3>Extensibility</h3>
<p>The code is designed to be simple, modular, and hack-friendly.<br>
You can easily:</p>
<ul>
<li>
<p>Integrate advanced trackers (DeepSORT, ByteTrack, etc.)</p>
</li>
<li>
<p>Add AI-based anomaly detection</p>
</li>
<li>
<p>Extend to multiple zones or CCTV feeds</p>
</li>
<li>
<p>Connect to alerting systems (SMS, IoT triggers, etc.)</p>
</li>
</ul>
<hr>
<h3>Use Case</h3>
<p>This system can serve as a foundation for:</p>
<ul>
<li>
<p>Metro / railway platform safety systems</p>
</li>
<li>
<p>Crowd management and surveillance</p>
</li>
<li>
<p>Smart city public safety research</p>
</li>
</ul>
<hr>
<h3>Summary</h3>
<p>A real-time, open-source metro monitoring system using YOLO/HOG for person detection, centroid tracking, safety line intrusion detection, and crowd density analytics — built for extensibility and community contribution.</p>
<hr>


## Screenshots 
![ss](https://github.com/user-attachments/assets/e85c9e92-2888-40e5-b20f-933d8a6e0bfa)
