# AWS
Aws deploying a instance which can go live and we can access it anytime from anywhere over the world ,using userdata to install appache server and lauch a simple static page to test the working of the ec2 instance 
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd

cat <<'EOF' > /var/www/html/index.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>ProLift Gym</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 0; background: #f5f6fa; color: #333;}
    header { background: #262a37; color: #fff; padding: 20px 0; text-align: center;}
    .nav-toggle {display: none; font-size: 2rem; cursor: pointer;}
    nav { margin: 0 auto; max-width: 900px;}
    nav a { color: #fff; text-decoration: none; margin: 0 15px; font-weight: 500; transition: color 0.2s;}
    nav a:hover { color: #4f8ef7;}
    .nav-list {display: flex; justify-content: center; list-style: none; padding: 0;}
    .hero {
      background: url('data:image/svg+xml;utf8,<svg width="1600" height="320" xmlns="http://www.w3.org/2000/svg"><rect fill="%234f8ef7" width="1600" height="320"/><text x="800" y="180" font-size="70" fill="white" text-anchor="middle" font-family="Arial">ProLift Gym</text></svg>') center/cover;
      min-height: 300px; display: flex; align-items: center; justify-content: center; color: #fff; text-shadow: 2px 2px 10px #222;
    }
    .hero h1 { font-size: 3rem;}
    .container { max-width: 900px; margin: 30px auto; padding: 0 15px;}
    .cards { display: flex; flex-wrap: wrap; gap: 25px; margin-top: 20px;}
    .card { background: #fff; border-radius: 8px; box-shadow: 0 4px 16px rgba(0,0,0,0.1); padding: 24px; flex: 1 1 260px; min-width: 220px; transition: transform 0.15s; cursor:pointer; }
    .card:hover { transform: translateY(-5px) scale(1.03); box-shadow: 0 6px 24px rgba(79,142,247,0.15);}
    .card-image {
      width: 80px; height: 80px; display: block; margin: 0 auto 12px auto; border-radius:50%; background: #ecf0f7; object-fit:cover;
    }
    .card-details { display:none; margin-top:10px; color: #444;}
    .card.active .card-details { display: block;}
    form { max-width: 400px; margin: 0 auto;}
    label { display: block; margin: 12px 0 4px;}
    input, textarea { width: 100%; padding: 8px; border-radius: 4px; border: 1px solid #ccc;}
    button { margin-top: 12px; padding: 10px 24px; border-radius: 4px; background: #262a37; color: #fff; border: none; font-weight: 600; cursor: pointer;}
    .error { color: #c0392b; font-size: 0.95em;}
    footer { background: #222; color: #bbb; text-align: center; padding: 18px 0; margin-top: 50px;}
    @media (max-width: 700px) {
      .cards { flex-direction: column; gap: 16px;}
      .hero h1 { font-size: 2rem;}
      .nav-list { display: none; flex-direction: column; }
      .nav-list.active { display: flex;}
      .nav-toggle {display:inline;}
    }
  </style>
</head>
<body>
  <!-- truncated: you can paste the rest of the body here -->
</body>
</html>
EOF
