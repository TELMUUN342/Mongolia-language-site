# Mongolia-language-site
Mongolian language learning and assistance platform with built-in translator, dictionary, and grammar rules. Easy to use, partially automated, and includes premium 
const express = require('express');
const cors = require('cors');
const app = express();
const port = 5000;

app.use(cors());

// Орчуулгын API
app.get('/translate', (req, res) => {
  const word = req.query.word;
  res.json({ translated: `Орчуулсан үг: ${word}` });
});

app.listen(port, () => {
  console.log(`Сервер http://localhost:${port} дээр ажиллаж байна`);
});
const mongoose = require('mongoose');

const WordSchema = new mongoose.Schema({
  word: String,
  definition: String,
});

module.exports = mongoose.model('Word', WordSchema);
