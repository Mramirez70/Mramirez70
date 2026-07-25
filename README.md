<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hoja de Vida - Técnico en Desarrollo de Software</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Inter:wght@300;400;500;600;700&family=Poppins:wght@600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <style>
        :root {
            --bg-primary: #0f172a;
            --bg-card: #1e293b;
            --bg-card-hover: #334155;
            --accent-blue: #38bdf8;
            --accent-green: #4ade80;
            --accent-purple: #c084fc;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --border-color: #334155;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-main);
            line-height: 1.6;
            padding: 40px 20px;
            display: flex;
            justify-content: center;
        }

        .cv-container {
            max-width: 950px;
            width: 100%;
            background-color: #0b1329;
            border-radius: 16px;
            border: 1px solid var(--border-color);
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }

        /* Banner de Cabecera con Imagen de Código */
        .cv-header {
            position: relative;
            background: linear-gradient(135deg, rgba(15, 23, 42, 0.85), rgba(30, 41, 59, 0.95)), 
                        url('http://googleusercontent.com/image_collection/image_retrieval/14517140322337339580_0') center/cover no-repeat;
            padding: 45px 50px;
            border-bottom: 2px solid var(--accent-blue);
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 30px;
        }

        .header-content h1 {
            font-family: 'Poppins', sans-serif;
            font-size: 34px;
            color: #ffffff;
            margin-bottom: 6px;
            letter-spacing: -0.5px;
        }

        .header-content .subtitle {
            font-family: 'Fira Code', monospace;
            color: var(--accent-blue);
            font-size: 18px;
            font-weight: 500;
            margin-bottom: 18px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .contact-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 15px 25px;
            font-size: 14px;
            color: var(--text-muted);
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .contact-item i {
            color: var(--accent-green);
        }

        .header-badge {
            background: rgba(56, 189, 248, 0.1);
            border: 1px solid var(--accent-blue);
            padding: 12px 20px;
            border-radius: 12px;
            text-align: center;
            min-width: 180px;
        }

        .header-badge i {
            font-size: 28px;
            color: var(--accent-blue);
            margin-bottom: 6px;
        }

        .header-badge span {
            display: block;
            font-size: 13px;
            font-family: 'Fira Code', monospace;
            color: var(--text-main);
        }

        /* Cuerpo principal */
        .cv-body {
            padding: 40px 50px;
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 40px;
        }

        .section-title {
            font-family: 'Poppins', sans-serif;
            font-size: 20px;
            color: #ffffff;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 8px;
        }

        .section-title i {
            color: var(--accent-blue);
            font-size: 18px;
        }

        .profile-card {
            background-color: var(--bg-card);
            border-radius: 12px;
            padding: 22px;
            border: 1px solid var(--border-color);
            margin-bottom: 30px;
            font-size: 15px;
            color: var(--text-muted);
            line-height: 1.7;
        }

        /* Proyectos e Imagen */
        .project-card {
            background-color: var(--bg-card);
            border-radius: 12px;
            border: 1px solid var(--border-color);
            overflow: hidden;
            margin-bottom: 25px;
            transition: transform 0.2s ease;
        }

        .project-img {
            width: 100%;
            height: 160px;
            object-fit: cover;
            border-bottom: 1px solid var(--border-color);
        }

        .project-info {
            padding: 20px;
        }

        .project-title {
            font-size: 17px;
            font-weight: 600;
            color: var(--text-main);
            margin-bottom: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .project-title span {
            font-family: 'Fira Code', monospace;
            font-size: 12px;
            color: var(--accent-green);
            background: rgba(74, 222, 128, 0.1);
            padding: 3px 8px;
            border-radius: 6px;
        }

        .project-desc {
            font-size: 14px;
            color: var(--text-muted);
            margin-bottom: 12px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tag {
            font-family: 'Fira Code', monospace;
            font-size: 12px;
            background-color: #0f172a;
            color: var(--accent-blue);
            padding: 4px 10px;
            border-radius: 6px;
            border: 1px solid var(--border-color);
        }

        /* Lista de experiencia e historial */
        .timeline-item {
            position: relative;
            padding-left: 24px;
            margin-bottom: 25px;
            border-left: 2px solid var(--border-color);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -6px;
            top: 4px;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: var(--accent-blue);
        }

        .timeline-role {
            font-size: 16px;
            font-weight: 600;
            color: var(--text-main);
        }

        .timeline-company {
            font-size: 14px;
            color: var(--accent-green);
            margin-bottom: 6px;
        }

        .timeline-desc {
            font-size: 14px;
            color: var(--text-muted);
        }

        /* Sidebar: Habilidades */
        .skills-group {
            margin-bottom: 25px;
        }

        .skills-group-title {
            font-size: 14px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: var(--text-muted);
            margin-bottom: 12px;
        }

        .skills-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .skill-item {
            background-color: var(--bg-card);
            padding: 10px 14px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            display: flex;
            align-items: center;
            justify-content: space-between;
            font-size: 14px;
        }

        .skill-item i {
            color: var(--accent-blue);
        }

        .soft-skills-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .soft-badge {
            background-color: rgba(192, 132, 252, 0.1);
            color: var(--accent-purple);
            border: 1px solid rgba(192, 132, 252, 0.3);
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 13px;
        }

        /* Botón de Impresión */
        .print-btn-wrapper {
            text-align: center;
            margin-bottom: 25px;
        }

        .print-btn {
            background: linear-gradient(135deg, var(--accent-blue), #0284c7);
            color: #ffffff;
            border: none;
            padding: 12px 28px;
            font-size: 15px;
            font-weight: 600;
            border-radius: 30px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(56, 189, 248, 0.3);
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .print-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(56, 189, 248, 0.5);
        }

        /* Optimización para Impresión (PDF) */
        @media print {
            body {
                background-color: #ffffff !important;
                color: #000000 !important;
                padding: 0 !important;
            }

            .print-btn-wrapper {
                display: none !important;
            }

            .cv-container {
                box-shadow: none !important;
                border: none !important;
                background-color: #ffffff !important;
                max-width: 100% !important;
            }

            .cv-header {
                background: #0f172a !important;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }

            .cv-body {
                padding: 30px 20px !important;
            }

            .profile-card, .project-card, .skill-item {
                background-color: #f8fafc !important;
                border: 1px solid #cbd5e1 !important;
                color: #1e293b !important;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }

            .project-title, .timeline-role, .section-title {
                color: #0f172a !important;
            }

            .project-desc, .timeline-desc, .profile-card {
                color: #334155 !important;
            }

            .tag {
                background-color: #e2e8f0 !important;
                color: #0369a1 !important;
                border: 1px solid #94a3b8 !important;
            }
        }

        @media (max-width: 768px) {
            .cv-header {
                flex-direction: column;
                align-items: flex-start;
                padding: 30px;
            }
            .cv-body {
                grid-template-columns: 1fr;
                padding: 25px;
            }
        }
    </style>
</head>
<body>

    <div style="width: 100%; max-width: 950px;">
        <!-- Botón para imprimir/guardar PDF -->
        <div class="print-btn-wrapper">
            <button class="print-btn" onclick="window.print()">
                <i class="fa-solid fa-print"></i> Guardar como PDF / Imprimir
            </button>
        </div>

        <div class="cv-container">
            <!-- HEADER CON BANNER DE CÓDIGO -->
            <header class="cv-header">
                <div class="header-content">
                    <h1>[Tu Nombre Completo]</h1>
                    <div class="subtitle">
                        <i class="fa-solid fa-code"></i> Técnico en Desarrollo de Software
                    </div>
                    <div class="contact-grid">
                        <div class="contact-item">
                            <i class="fa-solid fa-location-dot"></i> [Ciudad, Colombia]
                        </div>
                        <div class="contact-item">
                            <i class="fa-solid fa-phone"></i> [Tu Teléfono]
                        </div>
                        <div class="contact-item">
                            <i class="fa-solid fa-envelope"></i> [tu.correo@email.com]
                        </div>
                        <div class="contact-item">
                            <i class="fa-brands fa-github"></i> github.com/[tu-usuario]
                        </div>
                    </div>
                </div>
                <div class="header-badge">
                    <i class="fa-brands fa-laravel"></i>
                    <span>Backend Developer</span>
                    <span style="font-size: 11px; color: var(--accent-green); margin-top: 4px;">PHP & MySQL</span>
                </div>
            </header>

            <!-- CONTENIDO PRINCIPAL -->
            <div class="cv-body">
                <!-- COLUMNA IZQUIERDA -->
                <main>
                    <!-- Perfil Profesional -->
                    <section>
                        <h2 class="section-title">
                            <i class="fa-solid fa-user-gear"></i> Perfil Profesional
                        </h2>
                        <div class="profile-card">
                            Técnico en Desarrollo de Software enfocado en la construcción de soluciones backend con <strong>PHP (Laravel)</strong> y gestión de bases de datos relacionales en <strong>MySQL</strong>. Experiencia práctica en levantamiento de requerimientos de software, modelado de datos, arquitectura MVC y control de versiones con <strong>Git & GitHub</strong>. Destacado por alta adaptabilidad, razonamiento lógico, resolución eficiente de problemas y capacidad para trabajar en equipos ágiles de tecnología.
                        </div>
                    </section>

                    <!-- Proyectos Destacados (Con imagen de entorno de programación) -->
                    <section>
                        <h2 class="section-title">
                            <i class="fa-solid fa-laptop-code"></i> Proyectos de Software
                        </h2>

                        <div class="project-card">
                            <img src="http://googleusercontent.com/image_collection/image_retrieval/458621087971102627_0" alt="Entorno de programación de software" class="project-img">
                            <div class="project-info">
                                <div class="project-title">
                                    Sistema de Gestión Backend
                                    <span>Laravel + MySQL</span>
                                </div>
                                <p class="project-desc">
                                    Desarrollo de la arquitectura backend para una plataforma web empresarial. Implementación de consultas avanzadas, relaciones de base de datos y validaciones de seguridad.
                                </p>
                                <div class="project-tags">
                                    <span class="tag">PHP 8</span>
                                    <span class="tag">Laravel</span>
                                    <span class="tag">MySQL</span>
                                    <span class="tag">REST API</span>
                                    <span class="tag">Git</span>
                                </div>
                            </div>
                        </div>
                    </section>

                    <!-- Experiencia Laboral -->
                    <section>
                        <h2 class="section-title">
                            <i class="fa-solid fa-briefcase"></i> Experiencia Laboral
                        </h2>

                        <div class="timeline-item">
                            <div class="timeline-role">Auxiliar Logístico y de Operaciones</div>
                            <div class="timeline-company">Limpiemos Juntos / Servicios Generales</div>
                            <p class="timeline-desc">
                                • Control riguroso de procesos y atención al detalle en entornos exigentes.<br>
                                • Aplicación de resolución lógica de imprevistos y trabajo en equipo eficiente.<br>
                                • Cumplimiento continuo de metas operativas y estándares de calidad.
                            </p>
                        </div>
                    </section>
                </main>

                <!-- COLUMNA DERECHA / SIDEBAR -->
                <aside>
                    <!-- Habilidades Técnicas -->
                    <section class="skills-group">
                        <h2 class="section-title">
                            <i class="fa-solid fa-layer-group"></i> Skills
                        </h2>

                        <div class="skills-group-title">Backend & BD</div>
                        <div class="skills-list">
                            <div class="skill-item">
                                <span><i class="fa-brands fa-php"></i> PHP / Laravel</span>
                                <i class="fa-solid fa-check" style="color: var(--accent-green);"></i>
                            </div>
                            <div class="skill-item">
                                <span><i class="fa-solid fa-database"></i> MySQL</span>
                                <i class="fa-solid fa-check" style="color: var(--accent-green);"></i>
                            </div>
                            <div class="skill-item">
                                <span><i class="fa-brands fa-git-alt"></i> Git & GitHub</span>
                                <i class="fa-solid fa-check" style="color: var(--accent-green);"></i>
                            </div>
                        </div>

                        <div class="skills-group-title" style="margin-top: 20px;">Frontend & Análisis</div>
                        <div class="skills-list">
                            <div class="skill-item">
                                <span><i class="fa-brands fa-html5"></i> HTML5 / CSS3</span>
                            </div>
                            <div class="skill-item">
                                <span><i class="fa-solid fa-diagram-project"></i> Requerimientos UML</span>
                            </div>
                        </div>
                    </section>

                    <!-- Formación Académica -->
                    <section style="margin-bottom: 25px;">
                        <h2 class="section-title">
                            <i class="fa-solid fa-graduation-cap"></i> Educación
                        </h2>

                        <div class="timeline-item" style="margin-bottom: 15px;">
                            <div class="timeline-role" style="font-size: 14px;">Técnico en Desarrollo de Software</div>
                            <div class="timeline-company">SENA</div>
                        </div>

                        <div class="timeline-item" style="margin-bottom: 15px;">
                            <div class="timeline-role" style="font-size: 14px;">Técnico en Monitoreo Ambiental</div>
                            <div class="timeline-company">SENA</div>
                        </div>

                        <div class="timeline-item">
                            <div class="timeline-role" style="font-size: 14px;">Bachiller Académico</div>
                        </div>
                    </section>

                    <!-- Habilidades Blandas -->
                    <section>
                        <h2 class="section-title">
                            <i class="fa-solid fa-lightbulb"></i> Blandas
                        </h2>
                        <div class="soft-skills-badges">
                            <span class="soft-badge">Lógica de Programación</span>
                            <span class="soft-badge">Trabajo en Equipo</span>
                            <span class="soft-badge">Adaptabilidad</span>
                            <span class="soft-badge">Resolución de Problemas</span>
                            <span class="soft-badge">Pensamiento Analítico</span>
                        </div>
                    </section>
                </aside>
            </div>
        </div>
    </div>

</body>
</html>
