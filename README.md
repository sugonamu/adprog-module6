## Commit 1 Reflection Notes

In this milestone, I created a simple single-threaded TCP server that listens on port 7878. When I open the URL in the browser, the server prints “Connection established!” to the terminal, meaning it's receiving connections correctly. I learned how to use `TcpListener` in Rust and that the server runs in an infinite loop accepting streams.

## Commit 2 Reflection Notes

In this milestone, I made the server return a real HTML page. I learned how to read a file in Rust and build a proper HTTP response by including a status line and `Content-Length` header. When I opened the browser, the HTML was rendered correctly, showing that my server is sending valid responses.

![Commit 2 screen capture](/assets/images/commit2.png)

## Commit 3 Reflection Notes

In this milestone, I added simple request validation. The server now checks the first line of the HTTP request to determine the URL path. If the path is `/`, it serves `hello.html`. Otherwise, it serves `404.html`. I learned how to extract the request line using `BufReader` and match strings to control logic flow. This mimics how real servers route requests.

![Commit 3 screen capture](/assets/images/commit3.png)

## Commit 4 Reflection Notes

To simulate a delay, I added a `/sleep` route that pauses for 10 seconds. While testing, I visited `/sleep` and then immediately opened `/random`, which triggers a 404. Because the server is single-threaded, the 404 response also waited 10 seconds to show. I updated the `404.html` to clearly show when it appears. This helped me understand why single-threaded servers struggle with multiple users.

![Commit 4 screen capture](/assets/images/commit4.png)
