# Sever

: a server is thing that receives requests and does some work to computer response and sends it back.
**A request can be divided into CPU work and I/O work**  
insides of the server, one or more threads divded up the work between them.  
A thread can be thought of as a single worker that does work.  
A single thread of server has one worker handling requests.  
Severs handle requests using threads, which each independently hand requests.

A request can be broken up each table into parts need help in dark bule(CPU work) and parts that don't need help in light blue(I/O(Input/Output))  
and a thread ping pongs between them as each needs help.

### but what about when both parties need help at the same time?

the waiter(A thread) can only help one of them so, the other has to wait a little longer

# Non-Blocking I/O

; while a request is doing I/O, the thread is not stuck waiting for the request to finish.

# Blocking I/O

; Thread is stuck, or blocked waiting for I/O to finish

## Downsides of Non -blocking I/O

Only effective for I/O - heavy workloads.

Now I understood the reasons why Node js is appropriate to IO heavy workloads.
The link that i left down below was very useful to understand the concept of Non Blocking.
[Great Video](https://www.youtube.com/watch?v=wB9tIg209-8)
