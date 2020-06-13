
https://www.youtube.com/watch?v=kxNBkGmwzV8&list=WL&index=3

Go to https://start.spring.io/

1

Create Project as per screenshot

click on Generate > import in intellij

in src/main/java/resources/application.properties
>>server.port = 8090
>>or if server.port = 0 - it will start in new port every time

>create a new class CalculatorService.java

	@RestController
	public class CalculatorService {

    @GetMapping("/add/{x}/{y}")
    public int add(@PathVariable int x, @PathVariable int y){
        return x + y;
    }
Run CalcserviceApplication.java

http://localhost:8080/add/10/200

it will give : 210


for in form of JSON 
>create Response.java

	package com.calculator.service.calcservice;

	public class Response {

    private int x;
    private int y;

    private int result;

    public Response(int x, int y, int result) {
        this.x = x;
        this.y = y;
        this.result = result;
    }

    public int getX() {
        return x;
    }

    public int getY() {
        return y;
    }

    public int getResult() {
        return result;
    }
	}

in CalculaterService.java

add retun statement 
>return new Response(x, y, x+y);

and method type
>Response


http://localhost:8080/sub/100/20

http://localhost:8080/mul/10/20

http://localhost:8080/div/10/5

http://localhost:8080/mod/10/3

you can also run in terminal

> curl http://localhost:8080/mod/10/3