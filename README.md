<!DOCTYPE html>
<html lang="hy">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Հայկական նոր շուկա</title>
    <style>
        /* Ընդհանուր ոճեր */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f4f7f6;
            color: #333;
            line-height: 1.6;
        }

        header {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            text-align: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        header h1 {
            margin-bottom: 10px;
        }

        nav button {
            background: none;
            border: none;
            color: #1abc9c;
            font-size: 1rem;
            margin: 0 15px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s;
        }

        nav button:hover {
            color: white;
        }

        .container {
            max-width: 1200px;
            margin: 20px auto;
            display: flex;
            flex-wrap: wrap;
            padding: 0 20px;
        }

        .main-content {
            flex: 3;
            min-width: 300px;
            margin-right: 20px;
        }

        .card {
            background: white;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        .card h2 {
            color: #2c3e50;
            margin-bottom: 10px;
        }

        .card .date {
            color: #7f8c8d;
            font-size: 0.9rem;
            margin-bottom: 15px;
        }

        /* Աշխատող Կոճակ */
        .btn {
            display: inline-block;
            background: #1abc9c;
            color: white;
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            margin-top: 15px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: background 0.3s, transform 0.1s;
            text-decoration: none;
        }

        .btn:hover {
            background: #16a085;
        }

        .btn:active {
            transform: scale(0.95);
        }

        aside {
            flex: 1;
            min-width: 250px;
        }

        .sidebar-box {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            margin-bottom: 20px;
        }

        .sidebar-box h3 {
            color: #2c3e50;
            margin-bottom: 10px;
            border-bottom: 2px solid #1abc9c;
            padding-bottom: 5px;
        }

        /* Կոնտակտային բաժնի ոճերը */
        .contact {
            padding: 40px 0;
            background-color: #f4f7f6;
        }

        .contact .container {
            max-width: 600px;
            margin: 0 auto;
            display: block;
        }

        .section-title {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 20px;
        }

        .contact-form {
            background: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #2c3e50;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1rem;
        }

        .form-group textarea {
            resize: vertical;
        }

        .submit-btn {
            width: 100%;
            padding: 12px;
            font-size: 1rem;
            font-weight: bold;
        }

        .call-container {
            text-align: center;
            margin-top: 25px;
            border-top: 1px solid #eee;
            padding-top: 20px;
        }

        .call-btn {
            display: inline-block;
            background-color: #2980b9;
            color: white;
            padding: 12px 25px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: background 0.3s;
        }

        .call-btn:hover {
            background-color: #2171a3;
        }

        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 15px;
            margin-top: 20px;
        }

        /* --- ՄՈԴԱԼ ՊԱՏՈՒՀԱՆԻ ՈՃԵՐԸ (Pop-up) --- */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .modal-content {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
            position: relative;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .close-btn {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 24px;
            cursor: pointer;
            color: #7f8c8d;
        }

        .close-btn:hover {
            color: #000;
        }

        @media (max-width: 768px) {
            .container { flex-direction: column; }
            .main-content { margin-right: 0; }
        }
    </style>
</head>
<body>

    <header>
        <h1>Հայկական նոր շուկա</h1>
        <nav>
            <button onclick="navMenu('Գլխավոր էջ', 'Բարի գալուստ «Հայկական նոր շուկա» հարթակի գլխավոր էջ։ Այստեղ դուք կարող եք գտնել մեր առաջարկած բոլոր ծառայություններն ու պրոդուկտները։')">Գլխավոր</button>
            <button onclick="navMenu('Բլոգի բաժին', 'Այստեղ տեղադրված են մեր բոլոր նորություններն ու օգտակար հոդվածները։ Շուտով կավելանան նոր նյութեր դիզայնի վերաբերյալ։')">Բլոգ</button>
            <button onclick="navMenu('Մեր մասին տեղեկություն', 'Մենք ստեղծում ենք գեղեցիկ դիզայնով սլայդներ, նվերներ և օգնում ենք թվայնացնել ձեր ֆայլերը։ Շնորհակալություն մեզ ընտրելու համար։')">Մեր մասին</button>
        </nav> 
    </header>

    <div class="container">
        
        <main class="main-content">
            <article class="card">
                <h2>Մեր մասին</h2>
                <p>Ողջույն, ես վեբ դիզայներ եմ, պատրաստում եմ շատ զանազան պրոդուկտներ և փաստաթղթեր։ Մնացածը կտեսնես ներքևում, բարի դիտում և նախապես շնորհակալություն։</p>
            </article>

            <article class="card">
                <h2>Սահիկաշար (Slide)</h2>
                <p class="date">Հրապարակված է՝ Հունիս 9, 2026</p>
                <p>Ես պատրաստում եմ սահիկաշարեր գեղեցիկ դիզայնով, մաքուր և որակով...</p>
                <button class="btn" onclick="openModal('Սահիկաշարի պատվեր', 'Ավելին իմանալու կամ պատվիրելու համար զանգահարեք՝ +37477867634։ Մենք կապահովենք լավագույն դիզայնը ձեզ համար։')">Կարդալ ավելին</button>
            </article>

            <article class="card">
                <h2>Նվերներ ծննդյան առթիվ</h2>
                <p class="date">Հրապարակված է՝ Հունիս 9, 2026</p>
                <p>Ուզում ես նվեր սիրելիիդ համար կամ բարեկամիդ, մի շտապիր պատվիրել անորակ նվեր, պատվիրիր մեր էջից և չես փոշմանի...</p>
                <button class="btn" onclick="openModal('Նվերներ ծննդյան առթիվ', 'Պատրաստում ենք բացառիկ և գեղեցիկ նվերներ՝ ձեր նախընտրած նկարով կամ գրվածքով։ Մանրամասների համար կապվեք մեզ հետ։')">Կարդալ ավելին</button>
            </article>

            <article class="card">
                <h2>Word ֆայլերի պատրաստում</h2>
                <p class="date">Հրապարակված է՝ Հունիս 9, 2026</p>
                <p>Ձեռագիր տեքստը ուզում ես դարձնել տպագիր, դիմիր մեզ...</p>
                <button class="btn" onclick="openModal('Word ֆայլերի պատրաստում', 'Արագ և անսխալ պատրաստում ենք էլեկտրոնային Word ֆայլեր՝ ձեռագրից վերածելով տպագիր տեքստի։')">Կարդալ ավելին</button>
            </article>
        </main>

        <aside>
            <div class="sidebar-box">
                <h3>Հեղինակի մասին</h3>
                <p>Ողջույն, ես 15 տարեկան եմ, փորձառու դիզայներ եմ։</p>
            </div>
        </aside>

    </div>

    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="closeModal('myModal')">&times;</span>
            <h2 id="modalTitle">Վերնագիր</h2>
            <br>
            <p id="modalText">Բովանդակություն...</p>
        </div>
    </div>

    <div id="navModal" class="modal">
        <div class="modal-content">
            <span class="close-btn" onclick="closeModal('navModal')">&times;</span>
            <h2 id="navModalTitle">Մենյու</h2>
            <br>
            <p id="navModalText">Բովանդակություն...</p>
        </div>
    </div>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Գրեք Մեզ</h2>
            <div class="contact-form">
                
                                  <div class="form-group">
                        <label for="name">Անուն</label>
                        <input type="text" name="Անուն" id="name" required placeholder="Ձեր անունը">
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Էլ. հասցե</label>
                        <input type="email" name="Էլ. Հասցե" id="email" required placeholder="example@mail.com">
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Հաղորդագրություն</label>
                        <textarea name="Հաղորդագրություն" id="message" rows="5" required placeholder="Գրեք ձեր հաղորդագրությունը այստեղ..."></textarea>
                    </div>
                    
                    <button type="submit" class="btn submit-btn">Ուղարկել</button>
                </form>

                <div class="call-container">
                    <p style="color: #7f8c8d; font-size: 0.95rem;">Ունե՞ք հարցեր կամ շտապ պատվեր։</p>
                    <a href="tel:+37477867634" class="call-btn">
                        📞 Զանգահարել Հիմա
                    </a>
                </div>

            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Իմ Հարթակը. Բոլոր իրավունքները պաշտպանված են՝ «Կարապետյան Սուրեն»։</p>
    </footer>

    <script>
        // Ֆունկցիա՝ վերևի մենյուի կոճակների համար
        function navMenu(title, text) {
            document.getElementById("navModalTitle").innerText = title;
            document.getElementById("navModalText").innerText = text;
            document.getElementById("navModal").style.display = "flex";
        }

        // Ֆունկցիա՝ հոդվածի պատուհանը բացելու համար
        function openModal(title, text) {
            document.getElementById("modalTitle").innerText = title;
            document.getElementById("modalText").innerText = text;
            document.getElementById("myModal").style.display = "flex";
        }

        // Ընդհանուր ֆունկցիա՝ պատուհան փակելու համար
        function closeModal(modalId) {
            document.getElementById(modalId).style.display = "none";
        }

        // Փակել պատուհանները, եթե սեղմում ենք պատուհանից դուրս
        window.onclick = function(event) {
            let articleModal = document.getElementById("myModal");
            let navigationModal = document.getElementById("navModal");
            
            if (event.target == articleModal) {
                articleModal.style.display = "none";
            }
            if (event.target == navigationModal) {
                navigationModal.style.display = "none";
            }
        }
    </script>

</body>
</html>
