# Javascript example

```javascript?test
app.post("/api/login", (req, res) => {
  const user = {
    id: 1,
    username: "john",
    email: "john@gmail.com"
  };
  ![jwt].![sign]({ user }, "secretkey", (err, token) => {
    res.![json]({
      token
    });
  });
});
```
