<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Joshua · backend developer</title>
    <!-- Font Awesome for icons (clean, professional) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Font for subtle elegance -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #f9fafc;
            color: #1e293b;
            line-height: 1.5;
            padding: 2rem 1.5rem;
            display: flex;
            justify-content: center;
        }

        .readme-card {
            max-width: 1100px;
            width: 100%;
            background: white;
            border-radius: 2rem;
            box-shadow: 0 25px 50px -12px rgba(0,0,0,0.15);
            overflow: hidden;
            border: 1px solid #edf2f7;
        }

        /* header area */
        .profile-header {
            background: linear-gradient(145deg, #0b1120 0%, #1a2639 100%);
            padding: 2.5rem 2.5rem 1.8rem 2.5rem;
            color: white;
        }

        .name-title h1 {
            font-size: 2.8rem;
            font-weight: 600;
            letter-spacing: -0.02em;
            margin-bottom: 0.25rem;
            line-height: 1.2;
        }

        .name-title h1 span {
            color: #b1c5f0;
            font-weight: 400;
        }

        .subhead {
            font-size: 1.2rem;
            font-weight: 400;
            color: #b0c4de;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            flex-wrap: wrap;
        }

        .subhead i {
            color: #5f7eb0;
        }

        .badge-container {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
            margin: 1.5rem 0 0.8rem 0;
        }

        .badge {
            background: rgba(255,255,255,0.08);
            backdrop-filter: blur(4px);
            padding: 0.35rem 1rem;
            border-radius: 40px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid rgba(255,255,255,0.15);
            color: #e9f0ff;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .badge i {
            font-size: 0.9rem;
            color: #a0c0ff;
        }

        /* main layout two columns */
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1.1fr;
            gap: 1.8rem;
            padding: 2.2rem 2.5rem;
        }

        /* cards */
        .section-card {
            background: #ffffff;
            border-radius: 1.5rem;
            padding: 1.6rem 1.8rem;
            box-shadow: 0 8px 20px -6px rgba(0, 20, 40, 0.08);
            border: 1px solid #eef2f6;
            transition: all 0.2s;
            height: fit-content;
        }

        .section-card:hover {
            border-color: #cbd5e1;
            box-shadow: 0 15px 25px -12px rgba(0,35,70,0.1);
        }

        .section-title {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.3rem;
            font-weight: 600;
            letter-spacing: -0.01em;
            margin-bottom: 1.6rem;
            border-bottom: 2px solid #f1f4f9;
            padding-bottom: 0.8rem;
            color: #0f182a;
        }

        .section-title i {
            color: #2563eb;
            font-size: 1.4rem;
            width: 1.8rem;
        }

        /* tech stack chips */
        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tech-chip {
            background: #f1f5f9;
            padding: 0.5rem 1.2rem;
            border-radius: 40px;
            font-size: 0.95rem;
            font-weight: 500;
            color: #1e293b;
            border: 1px solid #e2e8f0;
            transition: 0.15s;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .tech-chip i {
            font-size: 1rem;
            color: #3b5b9b;
        }

        .tech-chip:hover {
            background: #e6edf8;
            border-color: #a0b8d4;
            transform: translateY(-1px);
        }

        /* stat items */
        .stat-row {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin: 1.2rem 0;
        }

        .stat-icon {
            width: 2.8rem;
            height: 2.8rem;
            background: #f0f4fe;
            border-radius: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #1e4a8b;
            font-size: 1.3rem;
        }

        .stat-content {
            flex: 1;
        }

        .stat-label {
            font-size: 0.9rem;
            color: #59748f;
            font-weight: 500;
            letter-spacing: 0.3px;
        }

        .stat-number {
            font-size: 1.9rem;
            font-weight: 600;
            color: #0b1f33;
            line-height: 1.2;
        }

        .stat-desc {
            color: #3d5a78;
            font-size: 0.95rem;
        }

        .graph-placeholder {
            background: #f2f6fd;
            border-radius: 20px;
            padding: 1.2rem;
            margin: 1rem 0;
            border: 1px dashed #bac8dc;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            color: #2d3f5e;
            font-weight: 500;
        }

        .graph-placeholder i {
            font-size: 2rem;
            color: #3b6cb0;
        }

        /* contact row */
        .contact-links {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 1.4rem;
            align-items: center;
        }

        .contact-btn {
            background: white;
            border: 1px solid #dde3ea;
            border-radius: 40px;
            padding: 0.65rem 1.5rem;
            font-size: 1rem;
            font-weight: 500;
            color: #1f2a41;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: 0.15s;
            text-decoration: none;
        }

        .contact-btn i {
            font-size: 1.2rem;
            color: #2b4f8e;
        }

        .contact-btn:hover {
            background: #f0f5ff;
            border-color: #6c8fc7;
            color: #0c1a31;
            transform: scale(1.02);
        }

        .btn-email i { color: #d44638; }
        .btn-linkedin i { color: #0a66c2; }
        .btn-portfolio i { color: #d46b1e; }

        .footer-wave {
            background: #0e1624;
            color: #8899bb;
            padding: 1.2rem 2.5rem;
            font-size: 0.9rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            border-top: 1px solid #293445;
        }

        .footer-wave i {
            color: #5f7eb0;
            margin: 0 4px;
        }

        hr {
            border: none;
            border-top: 2px solid #eef3f8;
            margin: 0.5rem 0 1.5rem 0;
        }

        .small-note {
            color: #596f88;
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* right column specific */
        .project-item {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .project-dot {
            width: 10px;
            height: 10px;
            background: #2563eb;
            border-radius: 20px;
            margin-top: 0.5rem;
        }

        .project-name {
            font-weight: 600;
            font-size: 1.1rem;
        }

        .project-desc {
            color: #415a77;
            font-size: 0.95rem;
        }

        @media (max-width: 750px) {
            .main-grid {
                grid-template-columns: 1fr;
                padding: 1.8rem;
            }
            .profile-header {
                padding: 1.8rem;
            }
            .name-title h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="readme-card">
        <!-- dark header area with name & role + badges -->
        <div class="profile-header">
            <div class="name-title">
                <h1>Joshua <span>// backend</span></h1>
                <div class="subhead">
                    <i class="fas fa-server"></i>  make things work behind the scenes 
                    <span style="opacity:0.5;">—</span> 
                    <i class="fas fa-code-branch"></i> clean, scalable logic
                </div>
            </div>
            <!-- minimal tech badges (professional) -->
            <div class="badge-container">
                <span class="badge"><i class="fab fa-php"></i> PHP</span>
                <span class="badge"><i class="fas fa-database"></i> MySQL</span>
                <span class="badge"><i class="fab fa-html5"></i> HTML5</span>
                <span class="badge"><i class="fab fa-css3-alt"></i> CSS3</span>
                <span class="badge"><i class="fab fa-linux"></i> Linux</span>
                <span class="badge"><i class="fab fa-git-alt"></i> Git</span>
                <span class="badge"><i class="fas fa-terminal"></i> Backend</span>
            </div>
            <!-- subtle note: experience -->
            <div style="margin-top: 1.2rem; color:#9bb5da; font-size:0.9rem; display: flex; gap: 2rem; flex-wrap: wrap;">
                <span><i class="far fa-clock" style="margin-right: 6px;"></i> 5+ years crafting APIs & services</span>
                <span><i class="fas fa-check-circle" style="margin-right: 6px; color:#75a5e0;"></i> available for opportunities</span>
            </div>
        </div>

        <!-- main two column layout -->
        <div class="main-grid">
            <!-- LEFT COLUMN: stats, overview, contact, contribution -->
            <div>
                <!-- GitHub stats card -->
                <div class="section-card">
                    <div class="section-title">
                        <i class="fas fa-chart-line"></i> GitHub activity
                    </div>
                    <div class="stat-row">
                        <div class="stat-icon"><i class="fas fa-code"></i></div>
                        <div class="stat-content">
                            <div class="stat-label">total contributions (2025)</div>
                            <div class="stat-number">1,842</div>
                            <div class="stat-desc">+412 from last quarter</div>
                        </div>
                    </div>
                    <div style="display: flex; gap: 1.5rem; justify-content: space-between; flex-wrap: wrap;">
                        <div>
                            <span style="color:#577a9e;">public repos</span>
                            <div style="font-weight:700; font-size: 1.7rem;">24</div>
                        </div>
                        <div>
                            <span style="color:#577a9e;">stars earned</span>
                            <div style="font-weight:700; font-size: 1.7rem;">139</div>
                        </div>
                        <div>
                            <span style="color:#577a9e;">followers</span>
                            <div style="font-weight:700; font-size: 1.7rem;">86</div>
                        </div>
                    </div>
                    <hr>
                    <!-- visual representation like graph -->
                    <div class="graph-placeholder">
                        <i class="fas fa-chart-bar"></i>
                        <span> contribution activity &nbsp; <strong>▁▂▃▄▆▇█▇▆▅▄▃▂</strong> </span>
                        <span style="font-size:0.85rem; background:#e1eaf3; padding:2px 10px; border-radius:30px;">#backend</span>
                    </div>
                    <!-- streak simulated in clean way -->
                    <div style="display: flex; gap: 0.8rem; align-items: center; margin-top: 0.8rem;">
                        <i class="fas fa-fire" style="color: #f57c00; font-size: 1.8rem;"></i>
                        <div>
                            <span style="font-weight:600;">current streak</span>
                            <span style="background: #eef3fc; padding:0.2rem 0.9rem; border-radius: 40px; margin-left: 0.8rem; font-weight:600;">16 days</span>
                            <div style="color: #3a5c7c; font-size: 0.9rem;">longest streak: 42 days</div>
                        </div>
                    </div>
                </div>

                <!-- Contact & let's connect -->
                <div class="section-card" style="margin-top: 1.5rem;">
                    <div class="section-title">
                        <i class="fas fa-paper-plane"></i> let's connect
                    </div>
                    <div class="contact-links">
                        <a href="#" class="contact-btn btn-email"><i class="fas fa-envelope"></i> joshua.dev@example.com</a>
                        <a href="#" class="contact-btn btn-linkedin"><i class="fab fa-linkedin"></i> linkedin/in/joshuabackend</a>
                        <a href="#" class="contact-btn btn-portfolio"><i class="fas fa-briefcase"></i> portfolio / resume</a>
                    </div>
                    <div class="small-note" style="margin-top: 1.2rem;">
                        <i class="fas fa-location-dot" style="color:#4d7eb3;"></i> remote · open to relocation
                    </div>
                </div>

                <!-- quick backend philosophy -->
                <div class="section-card" style="margin-top: 1.5rem; background: #fafdff;">
                    <div class="section-title">
                        <i class="fas fa-cog"></i> engineering focus
                    </div>
                    <ul style="list-style-type: none;">
                        <li style="margin-bottom: 0.8rem; display: flex; gap: 10px;"><i class="fas fa-database" style="color:#2c5784; width: 24px;"></i> <span>RESTful API design & integration</span></li>
                        <li style="margin-bottom: 0.8rem; display: flex; gap: 10px;"><i class="fas fa-shield-alt" style="color:#2c5784; width: 24px;"></i> <span>Secure authentication, SQL optimisation</span></li>
                        <li style="margin-bottom: 0.8rem; display: flex; gap: 10px;"><i class="fas fa-tachometer-alt" style="color:#2c5784; width: 24px;"></i> <span>Scalable backend architectures (LAMP, etc.)</span></li>
                        <li style="display: flex; gap: 10px;"><i class="fab fa-linux" style="color:#2c5784; width: 24px;"></i> <span>Server management & deployment (Git, CLI)</span></li>
                    </ul>
                </div>
            </div>

            <!-- RIGHT COLUMN: detailed tech stack, projects, tools -->
            <div>
                <!-- Tech Stack (vibrant but clean) -->
                <div class="section-card">
                    <div class="section-title">
                        <i class="fas fa-code"></i> tech stack
                    </div>
                    <div class="tech-grid">
                        <span class="tech-chip"><i class="fab fa-php"></i> PHP 8</span>
                        <span class="tech-chip"><i class="fas fa-database"></i> MySQL</span>
                        <span class="tech-chip"><i class="fab fa-html5"></i> HTML5</span>
                        <span class="tech-chip"><i class="fab fa-css3-alt"></i> CSS3</span>
                        <span class="tech-chip"><i class="fab fa-linux"></i> Linux</span>
                        <span class="tech-chip"><i class="fab fa-git-alt"></i> Git</span>
                        <span class="tech-chip"><i class="fas fa-code-branch"></i> Laravel</span>
                        <span class="tech-chip"><i class="fas fa-cloud"></i> Docker</span>
                        <span class="tech-chip"><i class="fas fa-lock"></i> JWT</span>
                        <span class="tech-chip"><i class="fas fa-robot"></i> RESTful</span>
                        <span class="tech-chip"><i class="fas fa-chart-simple"></i> Redis</span>
                    </div>
                </div>

                <!-- Recent project highlights (backend) -->
                <div class="section-card" style="margin-top: 1.5rem;">
                    <div class="section-title">
                        <i class="fas fa-folder-open"></i> featured backend work
                    </div>
                    <div class="project-item">
                        <div class="project-dot"></div>
                        <div>
                            <div class="project-name">inventory-core API</div>
                            <div class="project-desc">PHP/MySQL microservice for realtime stock — 3ms avg response.</div>
                        </div>
                    </div>
                    <div class="project-item">
                        <div class="project-dot"></div>
                        <div>
                            <div class="project-name">auth gateway (JWT)</div>
                            <div class="project-desc">standalone authentication layer used by 5+ internal apps.</div>
                        </div>
                    </div>
                    <div class="project-item">
                        <div class="project-dot"></div>
                        <div>
                            <div class="project-name">legacy optimiser</div>
                            <div class="project-desc">refactored SQL queries, cut page load from 4s to 0.3s.</div>
                        </div>
                    </div>
                    <div style="background: #edf3fe; border-radius: 30px; padding: 0.6rem 1.2rem; margin-top: 0.8rem;">
                        <i class="fas fa-code-pull-request" style="margin-right: 8px;"></i> 20+ merged PRs in OSS tools
                    </div>
                </div>

                <!-- contribution activity (simulated graph) + footer inside card -->
                <div class="section-card" style="margin-top: 1.5rem;">
                    <div class="section-title">
                        <i class="fas fa-calendar-alt"></i> contribution activity
                    </div>
                    <div style="display:flex; align-items: center; justify-content: space-between;">
                        <span style="color:#1f3b5c;">last 30 days:</span>
                        <span style="font-family: monospace; letter-spacing: 4px;">███▇██▅████▇███▆▅██▇███</span>
                    </div>
                    <!-- mini mock activity graph (professional clean representation) -->
                    <div style="background: #eef3f9; border-radius: 40px; padding: 1rem; margin: 1.2rem 0;">
                        <i class="fas fa-chart-gantt" style="margin-right: 6px; color:#235e9c;"></i> 
                        <span style="font-weight: 500;">weekly commits: 23 · 18 · 31 · 27</span>
                    </div>

                    <!-- secondary stack / tools inline -->
                    <div style="display: flex; gap: 0.5rem; flex-wrap: wrap; border-top: 1px dashed #cfddee; padding-top: 1rem;">
                        <span class="tech-chip" style="background:white;"><i class="fas fa-tools"></i> Postman</span>
                        <span class="tech-chip" style="background:white;"><i class="fas fa-cloud"></i> AWS (EC2)</span>
                        <span class="tech-chip" style="background:white;"><i class="fas fa-terminal"></i> bash</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- footer wave area -->
        <div class="footer-wave">
            <span><i class="fas fa-crown" style="opacity:0.8;"></i> backend engineer • clean code • problem solver</span>
            <span style="display: flex; gap: 10px;">
                <i class="fab fa-github"></i> /Watot12345 
                <i class="fas fa-circle" style="font-size: 0.3rem; align-self: center;"></i> 
                <i class="fas fa-envelope-open-text"></i> available
            </span>
        </div>
        <!-- hidden note: replace with your actual links/usernames -->
        <div style="font-size: 0.7rem; text-align: center; padding: 0.5rem; background: #f9fbfe; color: #7d92ab;">
            ⚙️ fully editable — insert your own stats, email, linkedin, portfolio. designed for job-ready presence.
        </div>
    </div>
</body>
</html>
