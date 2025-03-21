## Commit 1 Reflection Notes

In this milestone, I created a simple single-threaded TCP server that listens on port 7878. When I open the URL in the browser, the server prints “Connection established!” to the terminal, meaning it's receiving connections correctly. I learned how to use `TcpListener` in Rust and that the server runs in an infinite loop accepting streams.

## Commit 2 Reflection Notes

In this milestone, I made the server return a real HTML page. I learned how to read a file in Rust and build a proper HTTP response by including a status line and `Content-Length` header. When I opened the browser, the HTML was rendered correctly, showing that my server is sending valid responses.

![Commit 2 screen capture](/assets/images/commit2.png)
