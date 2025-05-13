<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Painel Escolar</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f6fa;
      margin: 0;
      transition: background-color 0.3s, color 0.3s;
    }

    .dark-mode {
      background-color: #2f3640;
      color: white;
    }

    .container {
      display: flex;
    }

    .sidebar {
      width: 220px;
      background-color: #2f3640;
      color: white;
      padding: 20px;
      min-height: 100vh;
    }

    .sidebar ul {
      list-style: none;
      padding: 0;
    }

    .sidebar li {
      margin-bottom: 35px;
    }

    .sidebar a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }

    .sidebar a:hover {
      color: #fbc531;
    }

    .main-content {
      flex: 1;
      padding: 30px;
    }

    .dashboard {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 20px;
    }

    .card {
      background-color: white;
      padding: 15px;
      border-left: 5px solid #00a8ff;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      font-size: 17px;
      position: relative;
    }

    .card span {
      display: block;
      margin-top: 5px;
      color: #666;
    }

    .entrega {
      color: #e84118;
      font-weight: bold;
      margin-top: 10px;
    }

    .btn-concluir {
      position: absolute;
      bottom: 10px;
      right: 10px;
      background: #44bd32;
      color: white;
      padding: 5px 10px;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }

    .notifications {
      background: #fbc531;
      padding: 10px;
      border-radius: 8px;
      margin-bottom: 20px;
      display: none;
    }

    .toggle-mode {
      position: absolute;
      right: 25px;
      top: 10px;
      background: #192a56;
      color: white;
      padding: 10px;
      border: none;
      cursor: pointer;
      border-radius: 5px;
      margin-bottom: 15px;
    }
  </style>
</head>
<body>
  <div class="container">
    <aside class="sidebar">
      <h2>Sttudy</h2>
      <nav>
        <ul>
            <li><a href="inicio.html">Início</a></li>
            <li><a href="prazo.html">Prazo</a></li>
            <li><a href="atividades.html">Atividades</a></li>
            <li><a href="perfil.html">Perfil</a></li>
        </ul>
      </nav>
    </aside>

    <main class="main-content">        
      <header>
        <h1>Bem-vindo(a), Aluno(a)!</h1>
        <button class="toggle-mode" onclick="toggleDarkMode()">Modo Escuro</button>
      </header>

      <div class="notifications" id="notificationBox">
        <p><strong>Aviso:</strong> Você tem atividades próximas do prazo de entrega!</p>
      </div>

      <section class="dashboard">
        <div class="card">
          Atividade<br>
          <span>Matemática - 07:45 às 8:30</span>
          <span class="entrega">Entrega: 15/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
        </div>
        <div class="card">
          Atividade<br>
          <span>Português - 8:35 às 9:30</span>
          <span class="entrega">Entrega: 18/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
        </div>
        <div class="card">
          Atividade<br>
          <span>Quimica - 09:30 às 10:00</span>
          <span class="entrega">Entrega: 18/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
          </div>
          <div class="card">    
          Atividade<br>
          <span>Fisica - 10:20 às 11:20</span>
          <span class="entrega">Entrega: 18/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
        </div>
        <div class="card">
          Atividade<br>
          <span>Literatura - 11:20 às 11:50</span>
          <span class="entrega">Entrega: 18/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
          </div>
          <div class="card">
          Atividade<br>
          <span>Biologia - 11:50 às 12:30</span>
          <span class="entrega">Entrega: 18/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
          </div>
          <div class="card">
          Atividade<br>
          <span>Projeto de Vida - 12:30 às 13:00</span>
          <span class="entrega">Entrega: 18/05/2025</span>
          <button class="btn-concluir" onclick="marcarConcluido(this)">Concluir</button>
          </div>
      </section>
    </main>
  </div>

  <script>
    function toggleDarkMode() {
      document.body.classList.toggle("dark-mode");
    }

    function marcarConcluido(elemento) {
      elemento.parentElement.style.opacity = "0.5";
      elemento.textContent = "Concluído";
      elemento.disabled = true;
    }

    window.onload = function() {
      document.getElementById("notificationBox").style.display = "block";
    };
  </script>
</body>
</html>
