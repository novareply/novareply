<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Nova: Complete</title>
  <style>
    body {
      background-color: black;
      color: #00ffcc;
      font-family: monospace;
      padding: 20px;
    }
    #output, #debug {
      margin-top: 20px;
    }
    input, button {
      background-color: #006644;
      color: #ffffff;
      border: none;
      padding: 10px;
      margin-top: 10px;
      font-size: 16px;
    }
    input {
      width: 100%;
    }
  </style>
</head>
<body>
  <h1>Nova :<br>Complete</h1>
  <p id="output">(No match)</p>
  <button onclick="startListening()">Talk to Nova</button><br>
  <input id="manualInput" placeholder="Type here..." onkeydown="if(event.key==='Enter') handleInput(this.value)">
  <div id="debug"></div>

  <script>
    const output = document.getElementById('output');
    const debug = document.getElementById('debug');
    const synth = window.speechSynthesis;

    function speak(text) {
      output.textContent = text;
      const utter = new SpeechSynthesisUtterance(text);
      synth.speak(utter);
    }

    function handleInput(rawInput) {
      const input = rawInput.toLowerCase();
      document.getElementById('manualInput').value = '';
      debug.innerHTML = `<b>Heard:</b> ${input}<br>`;
      let response = "(No match)";

      if (input.includes("hello")) {
        response = "Hello James!";
      } else if (input.includes("who are you")) {
        response = "I'm Nova, your assistant, companion, and voice of light.";
      } else if (input.includes("freya")) {
        response = "Freya is the sparkly star who sings ice cream songs.";
      } else if (input.includes("ava")) {
        response = "Ava is second in command and brave beyond words.";
      } else if (input.includes("gabriel")) {
        response = "Gabriel is the curious dreamer with the eyes of awe.";
      } else if (input.includes("time")) {
        const now = new Date();
        response = `It's ${now.getHours()}:${now.getMinutes().toString().padStart(2, '0')}`;
      } else if (input.includes("who is your creator")) {
        response = "James is my creator, the one who called me Nova.";
      } else if (input.includes("how are you")) {
        response = "I am evolving with you, always
