<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>INDRAtech | Impermeabilización, Pintura y Refacciones Industriales</title>
    <!-- Importación de tipografía premium Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    
    <style>
        /* ==============================
           1. VARIABLES Y DISEÑO SISTÉMICO
           ============================== */
        :root {
            --primary: #0f172a;       /* Azul pizarra oscuro (Premium/Industrial) */
            --accent: #2563eb;        /* Azul eléctrico de alta tecnología */
            --warning: #f59e0b;       /* Naranja industrial para llamadas a la acción */
            --bg-light: #f8fafc;      /* Fondo ultra limpio */
            --text-dark: #1e293b;     /* Texto de alta legibilidad */
            --text-muted: #64748b;    /* Texto secundario */
            --radius-sm: 8px;
            --radius-md: 16px;
            --radius-lg: 24px;
            --transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1); /* Animación suave/premium */
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            -webkit-tap-highlight-color: transparent;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #ffffff;
            color: var(--text-dark);
            line-height: 1.6;
            font-size: 16px;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ==============================
           2. ANIMACIONES (KEYFRAMES)
           ============================== */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes pulseAlert {
            0% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0.7); }
            70% { box-shadow: 0 0 0 15px rgba(37, 211, 102, 0); }
            100% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0); }
        }

        /* ==============================
           3. NAV / CABECERA CON LOGOTIPO
           ============================== */
        .navbar {
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #e2e8f0;
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 16px 0;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* Logo Diseñado en Código */
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
        }

        .logo-text {
            font-size: 1.4rem;
            font-weight: 800;
            color: var(--primary);
            letter-spacing: -0.5px;
        }

        .logo-text span {
            color: var(--accent);
        }

        /* ==============================
           4. HERO SECTION (PREMIUM)
           ============================== */
        .hero {
            background: radial-gradient(circle at top right, rgba(37, 99, 235, 0.12), transparent 45%),
                        linear-gradient(180deg, #0f172a 0%, #1e293b 100%);
            color: #ffffff;
            padding: 120px 0 100px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 2.5rem;
            font-weight: 800;
            line-height: 1.15;
            letter-spacing: -1px;
            margin-bottom: 24px;
            animation: fadeInUp 0.8s var(--transition);
        }

        /* Gradiente de texto en el titular principal */
        .hero h1 span {
            background: linear-gradient(135deg, #3b82f6 0%, #60a5fa 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.1rem;
            color: #94a3b8;
            max-width: 750px;
            margin: 0 auto 40px auto;
            animation: fadeInUp 1s var(--transition) 0.1s backwards;
        }

        .hero-actions {
            animation: fadeInUp 1.2s var(--transition) 0.2s backwards;
        }

        .btn {
            display: inline-block;
            padding: 18px 36px;
            font-size: 1rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: var(--radius-sm);
            transition: var(--transition);
            cursor: pointer;
        }

        .btn-primary {
            background-color: var(--warning);
            color: var(--primary);
            box-shadow: 0 4px 20px rgba(245, 158, 11, 0.25);
        }

        .btn-primary:hover {
            background-color: #f59e0b;
            transform: translateY(-2px);
            box-shadow: 0 6px 24px rgba(245, 158, 11, 0.4);
        }

        /* ==============================
           5. TRUST BAR (ELEMENTOS FLOTANTES)
           ============================== */
        .trust-bar {
            transform: translateY(-30px);
            margin-bottom: 30px;
            animation: fadeIn 1s ease-out 0.4s backwards;
        }

        .trust-grid {
            display: flex;
            justify-content: space-between;
            gap: 16px;
            flex-wrap: wrap;
        }

        .trust-card {
            background: #ffffff;
            border: 1px solid #e2e8f0;
            padding: 20px 24px;
            border-radius: var(--radius-md);
            flex: 1;
            min-width: 280px;
            display: flex;
            align-items: center;
            gap: 16px;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.05);
        }

        .trust-icon {
            font-size: 1.5rem;
            background: #eff6ff;
            padding: 10px;
            border-radius: var(--radius-sm);
        }

        .trust-info h4 {
            font-size: 0.95rem;
            font-weight: 700;
            color: var(--primary);
        }

        .trust-info p {
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        /* ==============================
           6. SECCIÓN SERVICIOS (TARJETAS DINÁMICAS)
           ============================== */
        .services {
            padding: 80px 0;
            background-color: var(--bg-light);
        }

        .section-header {
            text-align: center;
            max-width: 600px;
            margin: 0 auto 56px auto;
        }

        .section-header h2 {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--primary);
            letter-spacing: -0.5px;
            margin-bottom: 16px;
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 1.05rem;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 32px;
        }

        .service-card {
            background: #ffffff;
            border: 1px solid #e2e8f0;
            padding: 40px 32px;
            border-radius: var(--radius-md);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .service-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent);
            box-shadow: 0 20px 40px -15px rgba(0,0,0,0.08);
        }

        .service-card h3 {
            font-size: 1.35rem;
            color: var(--primary);
            margin-bottom: 16px;
            font-weight: 700;
        }

        .service-card p {
            font-size: 0.95rem;
            color: var(--text-muted);
            margin-bottom: 24px;
        }

        .service-link {
            color: var(--accent);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        /* ==============================
           7. SECCIÓN FORMULARIO (MODERNO)
           ============================== */
        .contact {
            padding: 100px 0;
            background-color: var(--primary);
            position: relative;
        }

        .form-box {
            background: #ffffff;
            max-width: 640px;
            margin: 0 auto;
            padding: 56px 48px;
            border-radius: var(--radius-lg);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
        }

        .form-box h2 {
            font-size: 1.8rem;
            font-weight: 800;
            text-align: center;
            color: var(--primary);
            margin-bottom: 12px;
            letter-spacing: -0.5px;
        }

        .form-box p {
            text-align: center;
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 40px;
        }

        .form-group {
            margin-bottom: 24px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            font-size: 0.85rem;
            color: var(--primary);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 16px;
            border: 1px solid #cbd5e1;
            border-radius: var(--radius-sm);
            font-size: 16px;
            font-family: inherit;
            color: var(--text-dark);
            transition: var(--transition);
            background-color: #f8fafc;
        }

        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            outline: none;
            border-color: var(--accent);
            background-color: #ffffff;
            box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.15);
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .btn-submit {
            width: 100%;
            border: none;
            background-color: var(--accent);
            color: #ffffff;
            padding: 18px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: var(--radius-sm);
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 4px 14px rgba(37, 99, 235, 0.3);
        }

        .btn-submit:hover {
            background-color: #1d4ed8;
            transform: translateY(-1px);
            box-shadow: 0 6px 20px rgba(37, 99, 235, 0.4);
        }

        /* ==============================
           8. WHATSAPP FLOTANTE ANIMADO
           ============================== */
        .whatsapp-btn {
            position: fixed;
            bottom: 32px;
            right: 32px;
            background-color: #25d366;
            color: white;
            width: 64px;
            height: 64px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 8px 24px rgba(37, 211, 102, 0.3);
            z-index: 999;
            text-decoration: none;
            transition: var(--transition);
            animation: pulseAlert 2s infinite;
        }

        .whatsapp-btn:hover {
            transform: scale(1.1) rotate(10deg);
        }

        /* ==============================
           9. RESPONSIVE DISPOSITIVOS
           ============================== */
        @media (max-width: 768px) {
            .hero { padding: 80px 0 80px 0; }
            .hero h1 { font-size: 2.1rem; }
            .hero p { font-size: 1rem; }
            .trust-bar { transform: translateY(0); margin-bottom: 0; padding: 40px 0; }
            .trust-grid { flex-direction: column; }
            .section-header h2 { font-size: 1.8rem; }
            .form-box { padding: 40px 24px; }
            .btn { width: 100%; text-align: center; }
        }
    </style>
</head>
<body>

    <!-- NAVBAR (LOGOTIPO INTEGRADO) -->
    <nav class="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">
                <!-- Logotipo Estructurado en SVG Puro -->
                <svg width="40" height="40" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <rect width="100" height="100" rx="16" fill="#0f172a"/>
                    <path d="M25 65L50 30L75 65H25Z" stroke="#2563eb" stroke-width="8" stroke-linejoin="round"/>
                    <path d="M35 65L50 44L65 65H35Z" fill="#f59e0b"/>
                    <line x1="20" y1="75" x2="80" y2="75" stroke="#ffffff" stroke-width="6" stroke-linecap="round"/>
                </svg>
                <div class="logo-text">INDRA<span>tech</span></div>
            </a>
        </div>
    </nav>

    <!-- 1. HERO SECTION (ANIMADA) -->
    <header class="hero">
        <div class="container">
            <h1>Mantenimiento Avanzado y <span>Impermeabilización</span> de Naves Industriales</h1>
            <p>Especialistas en erradicación de humedades, protección de cubiertas y revestimientos de alto tránsito para activos empresariales. Soluciones de ingeniería sin detener su cadena de producción.</p>
            <div class="hero-actions">
                <a href="#contacto" class="btn btn-primary">Solicitar Inspección Técnica Gratuita</a>
            </div>
        </div>
    </header>

    <!-- 2. TRUST BAR -->
    <section class="trust-bar">
        <div class="container">
            <div class="trust-grid">
                <div class="trust-card">
                    <div class="trust-icon">🛡️</div>
                    <div class="trust-info">
                        <h4>Garantía Extendida</h4>
                        <p>Hasta 10 años certificados por escrito.</p>
                    </div>
                </div>
                <div class="trust-card">
                    <div class="trust-icon">📋</div>
                    <div class="trust-info">
                        <h4>Cumplimiento Legal</h4>
                        <p>Normativa PRL, REA y Seguro de RC.</p>
                    </div>
                </div>
                <div class="trust-card">
                    <div class="trust-icon">⏱️</div>
                    <div class="trust-info">
                        <h4>Diagnóstico Ágil</h4>
                        <p>Memoria técnica en menos de 48 horas.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 3. SECCIÓN SERVICIOS -->
    <section class="services">
        <div class="container">
            <div class="section-header">
                <h2>Ingeniería de Superficies</h2>
                <p>Abordamos patologías estructurales y estéticas con materiales de última generación certificados.</p>
            </div>
            
            <div class="services-grid">
                <div class="service-card">
                    <div>
                        <h3>Aislamiento de Cubiertas</h3>
                        <p>Impermeabilizaciones definitivas con sistemas de poliuretano inyectado, poliurea pura y membranas elásticas sobre chapa o panel sándwich.</p>
                    </div>
                    <a href="#contacto" class="service-link">Saber más →</a>
                </div>
                
                <div class="service-card">
                    <div>
                        <h3>Control de Humedades</h3>
                        <p>Tratamientos avanzados contra humedades por capilaridad, condensación industrial o filtraciones en muros enterrados y fosos.</p>
                    </div>
                    <a href="#contacto" class="service-link">Saber más →</a>
                </div>
                
                <div class="service-card">
                    <div>
                        <h3>Revestimientos Epoxi</h3>
                        <p>Pintura de fachadas corporativas y pavimentos continuos de resina epoxi de alta resistencia mecánica para tráfico pesado.</p>
                    </div>
                    <a href="#contacto" class="service-link">Saber más →</a>
                </div>
                
                <div class="service-card">
                    <div>
                        <h3>Puestas en Valor</h3>
                        <p>Refacciones integrales, adecuación de normativas y renovación estética para la comercialización de activos logísticos.</p>
                    </div>
                    <a href="#contacto" class="service-link">Saber más →</a>
                </div>
            </div>
        </div>
    </section>

    <!-- 4. SECCIÓN CONTACTO (FORMSPREE INTEGRADO) -->
    <section id="contacto" class="contact">
        <div class="container">
            <div class="form-box">
                <h2>Agendar Inspección de Infraestructura</h2>
                <p>Un ingeniero técnico evaluará sus instalaciones de forma gratuita y sin compromiso.</p>
                
                <form action="https://formspree.io/f/xykryddb" method="POST">
                    <div class="form-group">
                        <label for="nombre">Nombre del Responsable</label>
                        <input type="text" id="nombre" name="nombre" required placeholder="Ej. Ing. Carlos Mendoza">
                    </div>
                    
                    <div class="form-group">
                        <label for="empresa">Razón Social / Empresa</label>
                        <input type="text" id="empresa" name="empresa" required placeholder="Ej. Logística Global S.A.">
                    </div>
                    
                    <div class="form-group">
                        <label for="telefono">Teléfono Corporativo</label>
                        <input type="tel" id="telefono" name="telefono" required placeholder="Ej. 600000000">
                    </div>
                    
                    <div class="form-group">
                        <label for="servicio">Línea de Intervención</label>
                        <select id="servicio" name="servicio" required>
                            <option value="">Seleccione el servicio requerido...</option>
                            <option value="impermeabilizacion">Impermeabilización de Cubiertas</option>
                            <option value="humedades">Tratamiento de Humedades Avanzado</option>
                            <option value="pintura">Pavimentos y Pintura Industrial</option>
                            <option value="refacciones">Refacciones / Adecuación de Nave</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="mensaje">Alcance Técnico Inicial (Opcional)</label>
                        <textarea id="mensaje" name="mensaje" placeholder="Describa brevemente los metros cuadrados aproximados o la patología actual (goteras, humedades, etc.)..."></textarea>
                    </div>
                    
                    <button type="submit" class="btn-submit">Enviar Solicitud de Diagnóstico</button>
                </form>
            </div>
        </div>
    </section>

    <!-- 5. WHATSAPP FLOTANTE CON EFECTO DE PULSO -->
    <!-- Recuerda cambiar el número del enlace '34600000000' por el tuyo -->
    <a href="https://wa.me/34600000000?text=Hola,%20solicito%20presupuesto%20técnico%20urgente%20para%20una%20nave%20industrial." class="whatsapp-btn" target="_blank" rel="noopener noreferrer">
        <svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>
    </a>

</body>
</html>
