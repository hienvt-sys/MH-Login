[Login.html](https://github.com/user-attachments/files/23447149/Login.html)
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Login Mockup - Prototype</title>
<style>
   :root{
     --bg: #F8FAFC;
     --card: #FFFFFF;
     --primary: #2563EB;
     --primary-hover: #1D4ED8;
     --text-main: #1E293B;
     --text-sec: #475569;
     --border: #CBD5E1;
     --error: #DC2626;
     --radius: 12px;
     font-family: 'Roboto', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
   }
   html,body{height:100%;margin:0;background:var(--bg);color:var(--text-main);}
   .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:40px;}
   .card{
     width:380px;background:var(--card);border-radius:var(--radius);box-shadow:0 4px 12px rgba(0,0,0,0.08);
     padding:36px;box-sizing:border-box;
   }
   .logo{width:88px;height:88px;border-radius:16px;background:#EEF2FF;display:flex;align-items:center;justify-content:center;margin:0 auto 12px;}
   .logo svg{width:48px;height:48px;opacity:0.85}
   h1{font-size:24px;margin:6px 0 18px;text-align:center;font-weight:700;color:var(--text-main);line-height:1.2}
   label{display:block;font-size:14px;color:var(--text-sec);margin-bottom:8px}
   .input{width:100%;height:44px;padding:10px 14px;border:1px solid var(--border);border-radius:6px;box-sizing:border-box;font-size:15px;color:var(--text-main);outline:none;transition:box-shadow .12s, border-color .12s}
   .input:focus{border-color:var(--primary);box-shadow:0 0 0 4px rgba(37,99,235,0.12)}
   .field{margin-bottom:14px;position:relative}
   .show-btn{position:absolute;right:12px;top:50%;transform:translateY(-50%);background:none;border:0;padding:4px;cursor:pointer;font-size:16px;color:#64748B}
   .forgot{display:block;text-align:right;margin-top:6px;font-size:14px;color:var(--primary);text-decoration:none}
   .btn{width:100%;height:44px;border-radius:6px;border:0;background:var(--primary);color:#fff;font-weight:600;font-size:16px;cursor:pointer;margin-top:12px}
   .btn:disabled{background:#93C5FD;color:#E2E8F0;cursor:not-allowed}
   .footer{margin-top:18px;text-align:center;color:var(--text-sec);font-size:14px}
   .footer a{color:var(--primary);text-decoration:none}
   @media (max-width:480px){
     .card{width:92%;padding:22px}
     h1{font-size:20px}
   }
</style>
</head>
<body>
<div class="wrap">
<div class="card" role="main" aria-labelledby="login-title">
<div class="logo" aria-hidden="true">
<svg viewBox="0 0 24 24" fill="none" stroke="#4B5563" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round">
<circle cx="12" cy="8" r="3.2"></circle>
<path d="M4.5 20a7.5 7.5 0 0 1 15 0"></path>
</svg>
</div>
<h1 id="login-title">Sign In to Your Account</h1>
<form id="loginForm" onsubmit="return false;" novalidate>
<div class="field">
<label for="email">Email Address</label>
<input id="email" class="input" type="email" placeholder="Enter your email" required />
</div>
<div class="field">
<label for="password">Password</label>
<input id="password" class="input" type="password" placeholder="Enter your password" required />
<button type="button" class="show-btn" aria-label="Toggle password visibility" onclick="togglePassword()">👁</button>
</div>
<a href="#" class="forgot">Forgot Password?</a>
<button id="submitBtn" class="btn" onclick="submitForm()">Sign In</button>
</form>
<div class="footer">Don't have an account? <a href="#">Sign Up</a></div>
</div>
</div>
<script>
function togglePassword(){
 var p = document.getElementById('password');
 if(p.type === 'password'){ p.type = 'text'; } else { p.type = 'password'; }
}
function submitForm(){
 var email = document.getElementById('email');
 var pwd = document.getElementById('password');
 var btn = document.getElementById('submitBtn');
 if(!email.value){ alert('Email is required'); email.focus(); return; }
 if(!pwd.value){ alert('Password is required'); pwd.focus(); return; }
 btn.disabled = true;
 btn.innerText = 'Signing...';
 setTimeout(function(){ alert('Signed in (demo)'); btn.disabled=false; btn.innerText='Sign In'; }, 800);
}
</script>
</body>
</html>
