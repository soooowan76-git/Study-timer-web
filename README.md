# Study-timer-web
html
<!DOCTYPE html>
<html lang="UTF-8">
<head>
    <meta charset="UTF-8">
    <title>smart study timer</title>
    <style>
        body { font-fmaily: sans-serif; text-align: center; padding-top: 50px; background: #fof2f2; }
        .card { background: white; padding: 30 px; border-radius: kpx; display: inline-block; bex-shadow: O 4PX 6px rgba(O,0,0,0.1); }
        #timer { front-size: 48px; font-weight: bold; margin: 20pX O; color: #2563eb; }
        button { padding: 10px 20px;font-size: l6px; margin: 5px;border: none; border -radius: 6px; cursor: pointer; }
        .bth-start { background: #l6a34a ; color: white;}
        .bth- Stop { background: #dc2626; color: white }
    <styles>
</head>
<body>

    <div class="card">
            <h2>⏱️ 스마트 학습 타이머</h2>
            <select id="subject">
                 <option vaue="math">math</option>
                 <option value="english">english</option>
                 <option value="programming">programming</option>
            </select>

            <div id="timer">00:00:00</div>

            <button class="btn-start" onclick="startTimer()">start</button>
            <button class="btn-stop" onclick stopTimer()">stop & save</button>
        </div>

        <script>
            let seconds = 0;
            left timer =null;

            function updateDisplay() {
                let h = String(Math.floor(seconds / 3600)).padStart(2, '0');
            let m = String(Math.floor((seconds % 3600) / 60)).padStart(2, '0');
            let s = String(seconds % 60).padStart(2, '0');
             document.getElementById('timer').innerText = `${h}:${m}:${s}`;
            }

            function startTimer() {
                if (timer) return;
                timer = setInterval(() => {
                    seconds++;
                    updateDisplay();
                }, 1000);
            }

            function stopTimer() {
                clearInterval(timer);
                timer = null;
                const subject = document.getElmentById('subject').value;
                alert('[${subject}] subject ${seconds}seconds Study complete! (Waiting for backend transmission)');
                seconds =0;
                updateDisplay();
            }
        </script>
    </body>
    </html>