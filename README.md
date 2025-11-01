<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TLevel Hub - Management & Administration Revision</title>
  <style>
    body { font-family: 'Segoe UI', Tahoma, sans-serif; margin: 0; background: #f4f6fb; color: #222; }
    header { background: #004aad; color: white; text-align: center; padding: 1.5rem; }
    nav { background: #003b8a; display: flex; justify-content: center; gap: 1rem; padding: 0.75rem; }
    nav a { color: white; text-decoration: none; font-weight: 500; }
    nav a:hover { text-decoration: underline; }
    .container { max-width: 900px; margin: 2rem auto; padding: 1rem; }
    .card { background: white; border-radius: 12px; padding: 1.5rem; margin-bottom: 1rem; box-shadow: 0 3px 6px rgba(0,0,0,0.1); }
    button { background: #004aad; color: white; border: none; padding: 0.5rem 1rem; border-radius: 8px; cursor: pointer; }
    button:hover { background: #003b8a; }
    footer { background: #003b8a; color: white; text-align: center; padding: 1rem; margin-top: 2rem; }
    input[type=text] { padding: 0.5rem; width: 80%; border-radius: 8px; border: 1px solid #ccc; }
  </style>
</head>
<body>
  <header>
    <h1>TLevel Hub</h1>
    <p>Management & Administration Revision Platform</p>
  </header>

  <nav>
    <a href="#home">Home</a>
    <a href="#topics">Topics</a>
    <a href="#quiz">Quizzes</a>
    <a href="#assistant">AI Assistant</a>
  </nav>

  <div class="container" id="home">
    <div class="card">
      <h2>Welcome to TLevel Hub</h2>
      <p>This website helps you revise for your T Level Management & Administration course. Explore revision notes, take quizzes, and even ask our AI assistant for help!</p>
    </div>
  </div>

  <div class="container" id="topics">
    <div class="card">
      <h2>Business Context</h2>
      <p>Learn about business environments, organisational structures, and stakeholder relationships. Understand how external factors affect decision-making.</p>
    </div>
    <div class="card">
      <h2>People Management</h2>
      <p>Explore leadership styles, motivation theories, and effective communication. Understand the key functions of HR and employee engagement.</p>
    </div>
    <div class="card">
      <h2>Project Management</h2>
      <p>Revise core project management principles, from planning and resource allocation to risk assessment and project delivery.</p>
    </div>
    <div class="card">
      <h2>Business Behaviours</h2>
      <p>Discover what makes a professional workplace, ethical decision-making, and the importance of teamwork and accountability.</p>
    </div>
  </div>

  <div class="container" id="quiz">
    <div class="card">
      <h2>Quick Quiz</h2>
      <p>Test your knowledge of management and administration topics.</p>
      <button onclick="startQuiz()">Start Quiz</button>
    </div>
  </div>

  <div class="container" id="assistant">
    <div class="card">
      <h2>AI Revision Assistant</h2>
      <p>Ask any question related to your T Level Management & Administration topics.</p>
      <input type="text" id="question" placeholder="Ask your AI assistant...">
      <button onclick="askAI()">Ask</button>
      <p id="answer" style="margin-top:1rem; font-weight:500;"></p>
    </div>
  </div>

  <footer>
    <p>&copy; 2025 TLevel Hub | Built for learners by learners</p>
  </footer>

  <script>
    const quiz = [
      { q: "What is management?", a: "The process of coordinating people and resources to achieve goals." },
      { q: "Name one leadership style.", a: "Autocratic or Democratic." },
      { q: "What does HR stand for?", a: "Human Resources." }
    ];

    function startQuiz() {
      let score = 0;
      quiz.forEach(item => {
        let userAns = prompt(item.q);
        if (userAns && userAns.toLowerCase().includes(item.a.split(' ')[0].toLowerCase())) score++;
      });
      alert(`You scored ${score} / ${quiz.length}`);
    }

    async function askAI() {
      const q = document.getElementById('question').value;
      if (!q) return alert('Please type a question!');
      document.getElementById('answer').innerText = 'Thinking...';
      // Placeholder - replace with your backend API endpoint for AI answers
      setTimeout(() => {
        document.getElementById('answer').innerText = `AI: Great question! Let's think about: ${q}`;
      }, 1000);
    }
  </script>
</body>
</html>
