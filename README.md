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

## Commit 5 Reflection Notes

This milestone upgraded my server to handle multiple requests concurrently using a ThreadPool. I created a thread pool that pre-spawns worker threads and assigns incoming connections as jobs. Now, requests to `/` or `/random` aren’t blocked even if `/sleep` is running. This helped me understand how thread scheduling and task queues work, and how efficient servers are designed.

![Commit 5 screen capture](/assets/images/commit5.png)

## Commit Bonus Reflection Notes

In this bonus milestone, I added a `build()` method to the `ThreadPool` struct as an alternative to the existing `new()` constructor. Functionally, it behaves the same, but using `build()` can offer more semantic clarity — especially if you’re following the builder pattern or planning for future customization. I tested the server and it still runs correctly with `build()`.

![Commit Bonus screen capture](/assets/images/bonus.png)
