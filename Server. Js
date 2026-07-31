const express = require('express');
const multer = require('multer');
const path = require('path');
const fs = require('fs');
const app = express();

const uploadDir = path.join(__dirname, 'uploads');
if (!fs.existsSync(uploadDir)) fs.mkdirSync(uploadDir);

const storage = multer.diskStorage({
  destination: uploadDir,
  filename: (req, file, cb) => cb(null, Date.now() + '-' + file.originalname)
});
const upload = multer({ storage });

app.get('/', (req, res) => {
  res.send(`
    <h2>Photo Upload</h2>
    <form action="/upload" method="post" enctype="multipart/form-data">
      <input type="file" name="photo" required />
      <button type="submit">Upload</button>
    </form>
  `);
});

app.post('/upload', upload.single('photo'), (req, res) => {
  res.send('Upload success! File: ' + req.file.filename);
});

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
