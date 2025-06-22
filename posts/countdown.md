# Countdown till graduation
Planning to graduate around here somewhere—fingers, toes, and everything crossed! I’ll be posting notes, sharing how classes are really going, and maybe venting a bit about how ready I am to finally say goodbye to Bloomsburg.
<br>

** <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Simple Countdown</title>
<style>
  #countdown {
    font-family: Arial, sans-serif;
    font-size: 1rem;
    color: #333;
    background: #f0f0f0;
    padding: 6px 10px;
    border-radius: 4px;
    display: inline-block;
    user-select: none;
  }
</style>
</head>
<body>

<div id="countdown">Loading...</div>

<script>
  // Target: December 12, this year, 12:00 PM (noon)
  const targetDate = new Date(new Date().getFullYear(), 11, 12, 12, 0, 0);

  const countdownEl = document.getElementById('countdown');

  function updateCountdown() {
    const now = new Date();
    const diff = targetDate - now;

    if (diff <= 0) {
      countdownEl.textContent = "The moment has arrived!";
      clearInterval(timerId);
      return;
    }

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    const minutes = Math.floor((diff / (1000 * 60)) % 60);
    const seconds = Math.floor((diff / 1000) % 60);

    countdownEl.textContent =
      (days > 0 ? days + 'd ' : '') +
      hours.toString().padStart(2, '0') + 'h ' +
      minutes.toString().padStart(2, '0') + 'm ' +
      seconds.toString().padStart(2, '0') + 's';
  }

  updateCountdown();
  const timerId = setInterval(updateCountdown, 1000);
</script>

</body>
</html>

**
