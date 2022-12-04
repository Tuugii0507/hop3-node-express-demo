"# hop3-node-express-task03" 

const express = require("express");
const app = express();

app.use(express.json());

var users = [];

app.get("/", (req, res) => {
  res.send("hello");
});

app.get("/greet/:name", (req, res) => {
  res.send("Hello, " + req.params.name);
});

app.post("/user", (req, res) => {
  users.push(req.body);
  console.log(users);
  res.send("user created");
});

app.patch("/user", (req, res) => {
  users.map((el) => {
    if (el.email === req.body.email) {
      (el.name = "TugsTuguldur"), (el.password = "12345");
    }
    console.log(users);
    res.send("user not found");
  });
});

app.listen(3000, () => {
  console.log("servers is running");
});
