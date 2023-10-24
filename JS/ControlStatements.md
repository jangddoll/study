# 제어문
## 제어문
* 프로그램에서 소스 실행 순서를 결정하는 제어문
* 특정 조건일 때 실행되거나 특정 부분을 반복하는 등의 방식으로 소스 흐름을 결정한다.
* 종류
  * if문 / if⋯else문 / 조건 연산자
  * switch문
  * for문
  * while문 /do⋯while문
  * break문 / continue문

## if문
1. if문
   ```
   if(조건) {명령문}
   ```
   * 조건을 만족하면 명령문을 실행한다

2. if⋯else문
   ```
   if(조건)
     {true일 경우 명령문}
   else
     {false일 경우 명령문}
   ```
   * 조건이 true면 if 뒤의 명령문을, false면 else 뒤의 명령문을 실행한다.
   * 조건과 실행문이 하나일 땐 중괄호를 생략할 수 있다.
       ```
       if(조건) 명령문
       else 명령문
       ```

3. 조건 연산자
   ```
   (조건) ? (참일 경우 실행문) : (거짓일 경우 실행문)
   ```
   * 조건과 실행문이 하나일 때 사용할 수 있다.

## switch문
* 변수를 여러 조건과 비교할 때 사용한다
* 복수의 if문 대신 사용할 수 있다.

  ```
  switch (비교할 변수) {
    case (비교할 조건) : 명령문
    break;
    case(비교할 조건) : 명령문
    break;
    default : 명령문
  }
  ```

* defalut는 모든 조건과 맞지 않을 때 실행되는 명령문이며, 작성하지 않아도 된다.
* switch문이 끝나거나 break문을 만나면 명령문의 실행이 끝난다.
  * break문이 없을 땐 다음 명령문이 조건을 만족하지 않아도 실행된다.
<br><br>

  > 예시
  > > break문을 썼을 때
  > > ```
  > > let a = 1 + 1;
  > > switch (1) {
  > >   case 1 :
  > >     document.write("비교하는 값보다 작습니다");
  > >   break;
  > >   case 2 :
  > >     document.write("비교하는 값과 같습니다");
  > >   break;
  > >   case 3 :
  > >     document.write("비교하는 값보다 큽니다");
  > >   break;
  > >   default:
  > >     document.write("비교하는 값과 일치하지 않습니다")
  > > ```
  > > ![image](https://github.com/jangddoll/study/assets/145321198/7a178008-9091-4115-8179-0f625f4199e6)

  >
  > > break문을 쓰지 않았을 때
  > > ```
  > > let a = 1 + 1;
  > > switch (1) {
  > >   case 1 :
  > >     document.write("비교하는 값보다 작습니다<br>");
  > >   case 2 :
  > >     document.write("비교하는 값과 같습니다<br>");
  > >   case 3 :
  > >     document.write("비교하는 값보다 큽니다<br>");
  > >   default :
  > >     document.write("비교하는 값과 일치하지 않습니다");
  > > ```
  > > ![image](https://github.com/jangddoll/study/assets/145321198/4959c2e6-9016-4e49-9b39-ae1a49bff323)
  > > * 조건을 만족하는 case 2 뒤의 모든 명령문이 실행된다

  * 여러 개의 조건에 같은 명령을 실행할 때, break문을 생략하면 된다
    ```
    let a = 3;

    switch(a) {
      case 1 + 1 :
        document.write("비교하는 값보다 작습니다");
      break;
      case 0 + 3 :
      case 1 + 2 :
      case 2 + 1 :
      case 3 + 0 :
        document.write("비교하는 값과 같습니다");
      break;
      case 2 + 2 :
        document.write("비교하는 값보다 큽니다");
      break;
    }
    ```
    ![image](https://github.com/jangddoll/study/assets/145321198/ee6047e3-6b10-4d98-aa3c-1372bdccb270)
    * case 0 + 3을 만족한 후 break가 없으므로 case 3 + 0 뒤의 break를 만나야 실행이 끝난다.

## for문
* 명령을 반복해서 실행한다.

   ```
   //1부터 100까지 더하는 for문
   let sum = 0;
  
   for(var i = 1; i < 101; i++) {
     sum += i;
   }
   document.write(sum);
   ```
   
* 'i = 1'은 for문에서만 사용할 카운터 변수를 선언하는 부분이다.
* 'i < 101'은 조건이며, true일 땐 중괄호 안의 명령문을 실행하다가, false가 되면(i가 101이 되면) for문을 종료하고 for문 밖의 명령문을 실행한다.
* 'i++'은 증감 연산자로 중괄호 안의 명령문 실행이 종료될 때마다 1씩 더하거나 뺀다.

## while문 / do⋯while문
* for문과의 비교
  * 공통점 : 명령문을 여러 번 반복 수행한다.
  * 차이점 : for문은 초기값이 있고 정해진 횟수만큼 반복하고, while문/do⋯while문은 조건을 만족할 때까지 반복한다.
* while문과 do⋯while문의 비교
  * 공통점 : 조건을 만족하면 반복 수행한다.
  * 차이점 : while문은 조건을 만족해야 수행하고, do⋯while문은 조건을 불만족해도 최소 1번은 수행한다.

## while문
* 조건을 만족하면 명령문을 수행한다.
  ```
  while(조건) {
    명령문
  }
  ```

## do⋯while문
* 명령문을 한 번 수행한 후 조건을 확인해 명령문을 반복 수행할지 결정한다.
  ```
  do {
    명령문
  }
  while (조건)
  ```

## break문
* 반복문의 명령문을 실행하던 중 break를 만나면 바로 반복을 종료한다.
  ```
  for(var i = 1; i < 6; i++) {
    if(i == 3) break;
    else document.write(i + "번째 반복문<br>");
  }
  ```
  * 결과
    ![image](https://github.com/jangddoll/study/assets/145321198/ee643f09-a8a2-4506-aa60-aa6689041a04)
    * i == 3부터 반복문이 종료된다.


## continue문
* 반복문의 명령을 실행하던 중 continue문을 만나면 해당 반복문을 수행하지 않고, 다음 반복으로 넘어간다.
  ```
  for(var i = 1; i < 6; i++) {
    if(i == 3) {
      continue;
    }
    else {
      document.write(i + "번째 반복문<br>");
    }
  }
  ```
  * 결과
    ![image](https://github.com/jangddoll/study/assets/145321198/bff0849b-a83a-401f-8101-07c25e21a90c)
    * 3번째 반복문은 건너뛰고 4번째부터 재개된다.

