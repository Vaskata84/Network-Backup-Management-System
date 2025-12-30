<!DOCTYPE html>
<html lang="bg">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Backup Manager - Документация</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }

        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 60px 40px;
            text-align: center;
        }

        header h1 {
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        header p {
            font-size: 1.3em;
            opacity: 0.95;
        }

        .badge {
            display: inline-block;
            padding: 8px 15px;
            background: rgba(255,255,255,0.2);
            border-radius: 20px;
            margin: 5px;
            font-size: 0.9em;
        }

        nav {
            background: #f8f9fa;
            padding: 20px;
            border-bottom: 3px solid #667eea;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav ul {
            list-style: none;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }

        nav a {
            color: #667eea;
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #764ba2;
        }

        .content {
            padding: 40px;
        }

        section {
            margin-bottom: 60px;
        }

        h2 {
            color: #667eea;
            font-size: 2.5em;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid #667eea;
        }

        h3 {
            color: #764ba2;
            font-size: 1.8em;
            margin: 30px 0 15px 0;
        }

        h4 {
            color: #555;
            font-size: 1.3em;
            margin: 20px 0 10px 0;
        }

        p {
            margin-bottom: 15px;
            text-align: justify;
        }

        ul, ol {
            margin-left: 30px;
            margin-bottom: 15px;
        }

        li {
            margin-bottom: 8px;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .feature-card {
            background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
            padding: 25px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }

        .feature-card h4 {
            color: #667eea;
            margin-top: 0;
        }

        code {
            background: #f4f4f4;
            padding: 2px 6px;
            border-radius: 3px;
            font-family: 'Courier New', monospace;
            font-size: 0.9em;
            color: #e83e8c;
        }

        pre {
            background: #2d2d2d;
            color: #f8f8f2;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            margin: 20px 0;
        }

        pre code {
            background: none;
            color: #f8f8f2;
            padding: 0;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        th {
            background: #667eea;
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }

        td {
            padding: 12px 15px;
            border-bottom: 1px solid #ddd;
        }

        tr:hover {
            background: #f8f9fa;
        }

        .alert {
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
            border-left: 5px solid;
        }

        .alert-success {
            background: #d4edda;
            border-color: #28a745;
            color: #155724;
        }

        .alert-info {
            background: #d1ecf1;
            border-color: #17a2b8;
            color: #0c5460;
        }

        .alert-warning {
            background: #fff3cd;
            border-color: #ffc107;
            color: #856404;
        }

        .alert-danger {
            background: #f8d7da;
            border-color: #dc3545;
            color: #721c24;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
            margin: 10px 5px;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .btn-revolut {
            background: linear-gradient(135deg, #00d4ff 0%, #0066ff 100%);
        }

        .donate-section {
            background: linear-gradient(135deg, #fff5e6 0%, #ffe6cc 100%);
            padding: 40px;
            border-radius: 15px;
            text-align: center;
            margin: 40px 0;
            border: 3px solid #ff9800;
        }

        .donate-section h3 {
            color: #ff6f00;
            font-size: 2em;
            margin-bottom: 20px;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            background: white;
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .stat-card .number {
            font-size: 2.5em;
            font-weight: bold;
            color: #667eea;
        }

        .stat-card .label {
            color: #666;
            margin-top: 10px;
        }

        footer {
            background: #2d3436;
            color: white;
            text-align: center;
            padding: 30px;
        }

        footer a {
            color: #667eea;
            text-decoration: none;
        }

        .emoji {
            font-size: 1.2em;
        }

        @media (max-width: 768px) {
            header h1 {
                font-size: 2em;
            }

            .content {
                padding: 20px;
            }

            nav ul {
                flex-direction: column;
                align-items: center;
            }
        }

        .highlight {
            background: linear-gradient(120deg, #667eea30 0%, #764ba230 100%);
            padding: 3px 8px;
            border-radius: 4px;
        }

        .command-box {
            position: relative;
        }

        .copy-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #667eea;
            color: white;
            border: none;
            padding: 5px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9em;
        }

        .copy-btn:hover {
            background: #764ba2;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><span class="emoji">📦</span> Backup Manager</h1>
            <p>Корпоративна Система за Архивиране на Мрежови Устройства</p>
            <div style="margin-top: 20px;">
                <span class="badge"><span class="emoji">🚀</span> v4.0</span>
                <span class="badge"><span class="emoji">⚡</span> 50x по-бързо</span>
                <span class="badge"><span class="emoji">🔧</span> 20+ производители</span>
                <span class="badge"><span class="emoji">🌐</span> 10,000 устройства</span>
            </div>
        </header>

        <nav>
            <ul>
                <li><a href="#overview">Преглед</a></li>
                <li><a href="#features">Функции</a></li>
                <li><a href="#devices">Устройства</a></li>
                <li><a href="#requirements">Изисквания</a></li>
                <li><a href="#installation">Инсталация</a></li>
                <li><a href="#quickstart">Бърз Старт</a></li>
                <li><a href="#configuration">Конфигурация</a></li>
                <li><a href="#usage">Използване</a></li>
                <li><a href="#troubleshooting">Проблеми</a></li>
                <li><a href="#donate">Дарение</a></li>
            </ul>
        </nav>

        <div class="content">
            <section id="overview">
                <h2><span class="emoji">🎯</span> Общ Преглед</h2>
                <p><strong>Backup Manager</strong> е готово за производствена употреба, корпоративно решение за автоматизиране на архивирането на конфигурации на мрежови устройства. Премахва необходимостта от ръчни процедури за архивиране, осигурява централизирано управление и гарантира проследяване на историята на конфигурациите на мрежовата инфраструктура.</p>

                <div class="stats">
                    <div class="stat-card">
                        <div class="number">50x</div>
                        <div class="label">По-бързо от v3.x</div>
                    </div>
                    <div class="stat-card">
                        <div class="number">10,000</div>
                        <div class="label">Устройства</div>
                    </div>
                    <div class="stat-card">
                        <div class="number">20+</div>
                        <div class="label">Производители</div>
                    </div>
                    <div class="stat-card">
                        <div class="number">30-60</div>
                        <div class="label">Минути за 10K</div>
                    </div>
                </div>

                <h3>Какъв Проблем Решава?</h3>
                <ul>
                    <li><strong>Ръчни Архиви:</strong> Премахва отнемащото време ръчно експортиране на конфигурации</li>
                    <li><strong>Загуба на Конфигурации:</strong> Предотвратява загуба на данни при повреди на устройства</li>
                    <li><strong>Одитна Следа:</strong> Поддържа пълна история на архивите за съответствие с регулациите</li>
                    <li><strong>Много Производители:</strong> Единно решение за разнообразно мрежово оборудване</li>
                    <li><strong>Мащабируемост:</strong> Обработва 10,000+ устройства с паралелна обработка</li>
                </ul>
            </section>

            <section id="features">
                <h2><span class="emoji">✨</span> Функционалности</h2>
                
                <div class="feature-grid">
                    <div class="feature-card">
                        <h4><span class="emoji">⚡</span> Паралелна Обработка</h4>
                        <p>10-100 едновременни архивирания на устройства с автоматично мащабиране на работниците според количеството устройства.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">📅</span> Автоматизирани Архиви</h4>
                        <p>Планирайте архиви на час, ден, седмица или по избран интервал с cron базирано планиране.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">🔌</span> Мулти-протокол</h4>
                        <p>SSH (предпочитан) с автоматично преминаване към Telnet. Поддръжка на enable пароли за Cisco.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">🔐</span> Управление на Креденшъли</h4>
                        <p>Сигурно съхранение с автоматични резервни опции. Приоритет на креденшъли и проследяване на успехи.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">🌐</span> Откриване на Мрежи</h4>
                        <p>Автоматично разпознаване на устройства чрез сканиране с 150 паралелни работници. Работи на фон.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">📊</span> История и Проследяване</h4>
                        <p>Пълна одитна следа със статус успех/неуспех. Търсене по IP, hostname, производител.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">🎨</span> Модерен Интерфейс</h4>
                        <p>Адаптивен уеб интерфейс с търсене, филтри, преглед и изтегляне на архиви.</p>
                    </div>

                    <div class="feature-card">
                        <h4><span class="emoji">🐳</span> Docker Базирано</h4>
                        <p>Лесно внедряване и преносимост. Едно команда deployment.</p>
                    </div>
                </div>

                <div class="alert alert-success">
                    <strong><span class="emoji">🎉</span> Ново в v4.0:</strong> Паралелна обработка прави системата 50x по-бърза! 1000 устройства се архивират за 3-5 минути вместо 2-3 часа.
                </div>
            </section>

            <section id="devices">
                <h2><span class="emoji">🔌</span> Поддържани Устройства</h2>
                
                <h3>Напълно Тествани</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Производител</th>
                            <th>Протокол</th>
                            <th>Забележки</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>MikroTik</strong></td>
                            <td>Telnet</td>
                            <td>RouterOS - поддръжка на shell режим</td>
                        </tr>
                        <tr>
                            <td><strong>Cisco</strong></td>
                            <td>SSH, Telnet</td>
                            <td>IOS, IOS-XE - поддръжка на enable парола</td>
                        </tr>
                        <tr>
                            <td><strong>Juniper</strong></td>
                            <td>SSH</td>
                            <td>JunOS - нативна SSH поддръжка</td>
                        </tr>
                        <tr>
                            <td><strong>Arista</strong></td>
                            <td>SSH</td>
                            <td>EOS - нативна SSH поддръжка</td>
                        </tr>
                        <tr>
                            <td><strong>HPE</strong></td>
                            <td>SSH, Telnet</td>
                            <td>Aruba суичове</td>
                        </tr>
                        <tr>
                            <td><strong>Dell</strong></td>
                            <td>SSH, Telnet</td>
                            <td>PowerConnect, OS10</td>
                        </tr>
                        <tr>
                            <td><strong>Huawei</strong></td>
                            <td>SSH, Telnet</td>
                            <td>VRP</td>
                        </tr>
                    </tbody>
                </table>

                <div class="alert alert-info">
                    <strong><span class="emoji">ℹ️</span> Забележка:</strong> Освен горните, системата поддържа още 15+ производители чрез генеричен профил: Ubiquiti, D-Link, TP-Link, Planet, Ruby Tech, Zyxel, Netgear и други.
                </div>
            </section>

            <section id="requirements">
                <h2><span class="emoji">💻</span> Системни Изисквания</h2>
                
                <h3>Минимални Изисквания</h3>
                <ul>
                    <li><strong>ОС:</strong> Linux (Ubuntu 20.04+, Debian 10+, CentOS 8+)</li>
                    <li><strong>Docker:</strong> 20.10+</li>
                    <li><strong>Docker Compose:</strong> 1.29+</li>
                    <li><strong>RAM:</strong> 1024 MB</li>
                    <li><strong>CPU:</strong> 2 ядра</li>
                    <li><strong>Диск:</strong> 10 GB (+ място за архиви)</li>
                    <li><strong>Мрежа:</strong> Достъп до устройства на порт 22 (SSH) и/или 23 (Telnet)</li>
                </ul>

                <h3>Препоръки за Различни Мащаби</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Устройства</th>
                            <th>RAM</th>
                            <th>CPU</th>
                            <th>Диск</th>
                            <th>Време</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>&lt; 100</td>
                            <td>512MB</td>
                            <td>2 ядра</td>
                            <td>10GB</td>
                            <td>1-2 мин</td>
                        </tr>
                        <tr>
                            <td>100-500</td>
                            <td>1-2GB</td>
                            <td>4 ядра</td>
                            <td>50GB</td>
                            <td>5-10 мин</td>
                        </tr>
                        <tr>
                            <td>500-2000</td>
                            <td>2-4GB</td>
                            <td>8 ядра</td>
                            <td>50GB SSD</td>
                            <td>10-30 мин</td>
                        </tr>
                        <tr>
                            <td>2000-10000</td>
                            <td>8-16GB</td>
                            <td>16 ядра</td>
                            <td>100GB SSD</td>
                            <td>30-60 мин</td>
                        </tr>
                    </tbody>
                </table>
            </section>

            <section id="installation">
                <h2><span class="emoji">🚀</span> Инсталация</h2>
                
                <h3>Стъпка 1: Инсталирайте Docker</h3>
                <div class="command-box">
                    <pre><code>curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
# Излезте и влезте отново</code></pre>
                </div>

                <h3>Стъпка 2: Инсталирайте Docker Compose</h3>
                <div class="command-box">
                    <pre><code>sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose</code></pre>
                </div>

                <h3>Стъпка 3: Изтеглете и Стартирайте Backup Manager</h3>
                <div class="command-box">
                    <pre><code># Създайте директория
mkdir -p ~/Backup
cd ~/Backup

# Изтеглете последната версия
wget https://github.com/Vaskata84/Network-Backup-Management-System/backup-manager/releases/latest/download/BACKUP-MANAGER-v4.0-FINAL.tar.gz

# Извлечете
tar -xzf BACKUP-MANAGER-v4.0-FINAL.tar.gz

# Стартирайте
docker-compose up -d

# Проверете статус
docker logs -f backup-manager-ultra</code></pre>
                </div>

                <div class="alert alert-success">
                    <strong><span class="emoji">✅</span> Готово!</strong> Отворете браузър на <code>http://your-server-ip:8086</code><br>
                    Вход: <code>admin</code> / <code>admin</code> (сменете паролата веднага!)
                </div>
            </section>

            <section id="quickstart">
                <h2><span class="emoji">🎓</span> Бърз Старт</h2>
                
                <h3>1. Добавете Креденшъли</h3>
                <ol>
                    <li>Отидете на <strong>Admin → Credentials</strong></li>
                    <li>Кликнете <strong>Add Credential</strong></li>
                    <li>Попълнете:
                        <ul>
                            <li>Име: <code>cisco-main</code></li>
                            <li>Производител: <code>CISCO</code></li>
                            <li>Потребител: <code>admin</code></li>
                            <li>Парола: <code>cisco123</code></li>
                            <li>Enable Парола: <code>enable123</code></li>
                            <li>Приоритет: <code>100</code></li>
                        </ul>
                    </li>
                    <li>Запазете</li>
                </ol>

                <h3>2. Добавете Устройства</h3>
                <ol>
                    <li>Отидете на <strong>Admin → Devices</strong></li>
                    <li>Кликнете <strong>Add Device</strong></li>
                    <li>Попълнете:
                        <ul>
                            <li>IP Адрес: <code>192.168.1.1</code></li>
                            <li>Hostname: <code>core-switch-01</code></li>
                            <li>Производител: <code>CISCO</code></li>
                            <li>Метод: <code>telnet</code> или <code>ssh</code></li>
                            <li>Порт: <code>23</code> (Telnet) или <code>22</code> (SSH)</li>
                        </ul>
                    </li>
                    <li>Запазете</li>
                </ol>

                <h3>3. Тествайте Ръчен Архив</h3>
                <ol>
                    <li>Отидете на <strong>Admin → Devices</strong></li>
                    <li>Кликнете <strong>Backups</strong> на устройството</li>
                    <li>Кликнете <strong>Test Backup</strong></li>
                    <li>Проследете прогреса в логовете</li>
                </ol>

                <h3>4. Планирайте Автоматични Архиви</h3>
                <ol>
                    <li>Отидете на <strong>Admin → Cron</strong></li>
                    <li>Кликнете <strong>Add Schedule</strong></li>
                    <li>Попълнете:
                        <ul>
                            <li>Име: <code>Дневни Архиви</code></li>
                            <li>Cron Израз: <code>0 2 * * *</code> (всеки ден в 2 ч.)</li>
                            <li>Скрипт: Изберете backup скрипта</li>
                            <li>Цел: <code>All Devices</code></li>
                        </ul>
                    </li>
                    <li>Активирайте и запазете</li>
                </ol>

                <div class="alert alert-info">
                    <strong><span class="emoji">💡</span> Съвет:</strong> Често използвани cron изрази:<br>
                    <code>0 * * * *</code> - Всеки час<br>
                    <code>0 2 * * *</code> - Всеки ден в 2 ч.<br>
                    <code>0 2 * * 0</code> - Всяка седмица<br>
                    <code>0 2 1 * *</code> - Всеки месец
                </div>
            </section>

            <section id="configuration">
                <h2><span class="emoji">⚙️</span> Конфигурация</h2>
                
                <h3>Настройка на Производителността</h3>
                <p>Редактирайте <code>docker-compose.yml</code>:</p>
                
                <pre><code>services:
  backup-manager:
    environment:
      # Часова зона
      - TZ=Europe/Sofia
      
      # Производителност (v4.0+)
      - MAX_WORKERS=50           # Паралелни работници (10-100)
      - WORKER_TIMEOUT=120       # Timeout на устройство (секунди)
      
      # Сигурност
      - SECRET_KEY=вашият-секретен-ключ</code></pre>

                <h3>Препоръчителни Настройки</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Устройства</th>
                            <th>MAX_WORKERS</th>
                            <th>RAM</th>
                            <th>CPU</th>
                            <th>Време</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>&lt; 100</td>
                            <td>10-20</td>
                            <td>512MB</td>
                            <td>2 ядра</td>
                            <td>1-2 мин</td>
                        </tr>
                        <tr>
                            <td>100-500</td>
                            <td>20-30</td>
                            <td>1GB</td>
                            <td>4 ядра</td>
                            <td>5-10 мин</td>
                        </tr>
                        <tr>
                            <td>500-2000</td>
                            <td>30-50</td>
                            <td>2GB</td>
                            <td>8 ядра</td>
                            <td>10-30 мин</td>
                        </tr>
                        <tr>
                            <td>2000-10000</td>
                            <td>50-100</td>
                            <td>4-8GB</td>
                            <td>16 ядра</td>
                            <td>30-60 мин</td>
                        </tr>
                    </tbody>
                </table>

                <div class="command-box">
                    <pre><code># Приложете промените
docker-compose restart</code></pre>
                </div>
            </section>

            <section id="usage">
                <h2><span class="emoji">📖</span> Ръководство за Използване</h2>
                
                <h3>Преглед на Архиви</h3>
                <ol>
                    <li>Отидете на <strong>Home</strong> (<code>/</code>)</li>
                    <li>Вижте всички скорошни архиви</li>
                    <li>Търсете по IP, hostname или производител</li>
                    <li>Кликнете <strong>View</strong> за преглед</li>
                    <li>Кликнете <strong>Download</strong> за изтегляне</li>
                </ol>

                <h3>Сканиране на Мрежа</h3>
                <ol>
                    <li>Отидете на <strong>Admin → Networks</strong></li>
                    <li>Кликнете <strong>Scan Network</strong></li>
                    <li>Сканирането работи на фон (можете да се разхождате)</li>
                    <li>Проследете прогреса в логовете:</li>
                </ol>

                <div class="command-box">
                    <pre><code>docker logs -f backup-manager-ultra | grep SCAN</code></pre>
                </div>

                <h3>Мониторинг</h3>
                <div class="command-box">
                    <pre><code># Реално време логове
docker logs -f backup-manager-ultra

# Последни 100 реда
docker logs --tail 100 backup-manager-ultra

# Проверка на ресурси
docker stats backup-manager-ultra</code></pre>
                </div>
            </section>

            <section id="troubleshooting">
                <h2><span class="emoji">🔧</span> Отстраняване на Проблеми</h2>
                
                <h3>Проблем: Архивирането Неуспява с "Authentication failed"</h3>
                <div class="alert alert-warning">
                    <strong>Решение:</strong>
                    <ol>
                        <li>Проверете креденшълите в <strong>Admin → Credentials</strong></li>
                        <li>Тествайте ръчно: <code>ssh admin@DEVICE_IP</code> или <code>telnet DEVICE_IP 23</code></li>
                        <li>Добавете или поправете креденшъла</li>
                        <li>Опитайте отново архивирането</li>
                    </ol>
                </div>

                <h3>Проблем: Устройството Изтича (Timeout)</h3>
                <div class="alert alert-warning">
                    <strong>Възможни причини:</strong>
                    <ul>
                        <li>Устройството е офлайн</li>
                        <li>Firewall блокира достъпа</li>
                        <li>Устройството е много бавно</li>
                    </ul>
                    <strong>Решение:</strong>
                    <pre><code># Тествайте свързаност
docker exec backup-manager-ultra ping -c 3 DEVICE_IP

# Увеличете timeout
# Редактирайте docker-compose.yml: WORKER_TIMEOUT=180
docker-compose restart</code></pre>
                </div>

                <h3>Проблем: SSH Banner Грешка</h3>
                <div class="alert alert-danger">
                    <strong>Грешка:</strong> <code>SSHException: Error reading SSH protocol banner</code><br>
                    <strong>Причина:</strong> Портът е зададен на SSH (22) но устройството е Telnet (23)<br>
                    <strong>Решение:</strong>
                    <pre><code>docker exec backup-manager-ultra sqlite3 /data/backup_manager.db \
  "UPDATE devices SET port=23 WHERE ip_address='192.168.1.1';"</code></pre>
                </div>

                <h3>Debug Режим</h3>
                <div class="command-box">
                    <pre><code># Тествайте ръчно за да видите точната грешка
docker exec -it backup-manager-ultra python3 -u /app/default_backup_script.py DEVICE_IP</code></pre>
                </div>
            </section>

            <section id="donate" class="donate-section">
                <h3><span class="emoji">☕</span> Харесва ли ви проекта?</h3>
                <p style="font-size: 1.2em; margin: 20px 0;">Ако Backup Manager ви помага в работата и желаете да подкрепите развитието на проекта, можете да ме поканите на кафе! <span class="emoji">😊</span></p>
                
                <p style="font-size: 1em; color: #666; margin: 20px 0;">Всяка подкрепа е добре дошла и мотивира за създаването на още полезни инструменти!</p>
                
                <a href="https://revolut.me/vasilwpj" target="_blank" class="btn btn-revolut" style="font-size: 1.2em; padding: 15px 40px;">
                    <span class="emoji">💳</span> Дарете чрез Revolut
                </a>
                
                <p style="margin-top: 30px; font-size: 0.9em; color: #888;">
                    <span class="emoji">🙏</span> Благодаря за подкрепата!<br>
                    Тя помага за поддръжката и разширяването на проекта.
                </p>
            </section>

            <section id="performance">
                <h2><span class="emoji">📊</span> Производителност</h2>
                
                <h3>Реални Резултати (v4.0)</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Устройства</th>
                            <th>v3.x (Последователно)</th>
                            <th>v4.0 (25 работници)</th>
                            <th>v4.0 (50 работници)</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>10</td>
                            <td>100с</td>
                            <td>15с</td>
                            <td>10с</td>
                        </tr>
                        <tr>
                            <td>100</td>
                            <td>17 мин</td>
                            <td>4 мин</td>
                            <td>2 мин</td>
                        </tr>
                        <tr>
                            <td>500</td>
                            <td>1.4 часа</td>
                            <td>20 мин</td>
                            <td>10 мин</td>
                        </tr>
                        <tr>
                            <td>1,000</td>
                            <td>2.8 часа</td>
                            <td>40 мин</td>
                            <td>20 мин</td>
                        </tr>
                        <tr style="background: #d4edda;">
                            <td><strong>5,000</strong></td>
                            <td><strong>14 часа</strong></td>
                            <td><strong>3.5 часа</strong></td>
                            <td><strong>1.7 часа</strong></td>
                        </tr>
                    </tbody>
                </table>

                <div class="alert alert-success">
                    <strong><span class="emoji">🚀</span> Впечатляващо:</strong> При 5,000 устройства, v4.0 е <span class="highlight">до 8 пъти по-бърз</span> от v3.x!
                </div>
            </section>
        </div>

        <footer>
            <p><strong>Backup Manager v4.0</strong></p>
            <p>Създадено с <span class="emoji" style="color: #e74c3c;">❤️</span> за Мрежови Инженери</p>
            <p style="margin-top: 20px;">
                <strong>Автор:</strong> Васил Добчев<br>
                <strong>Лиценз:</strong> MIT License<br>
                <strong>GitHub:</strong> <a href="https://github.com/Vaskata84/Network-Backup-Management-System">github.com/Vaskata84/Network-Backup-Management-System</a>
            </p>
            <p style="margin-top: 20px; font-size: 0.9em;">
                © 2025 Backup Manager. Всички права запазени.
            </p>
        </footer>
    </div>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            });
        });

        // Add copy buttons to code blocks
        document.querySelectorAll('pre').forEach(pre => {
            const button = document.createElement('button');
            button.className = 'copy-btn';
            button.textContent = 'Copy';
            button.addEventListener('click', () => {
                const code = pre.querySelector('code').textContent;
                navigator.clipboard.writeText(code).then(() => {
                    button.textContent = 'Copied!';
                    setTimeout(() => button.textContent = 'Copy', 2000);
                });
            });
            pre.parentElement.style.position = 'relative';
            pre.parentElement.appendChild(button);
        });
    </script>
</body>
</html>
