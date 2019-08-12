# 즉시 실행 함수 표현(IIFE, Immediately Invoked Function Expression)
은 정의되자마자 즉시 실행되는 Javascript Function 를 말한다.

<pre><code>
(function () {
    statements
})();
</pre></code>

이는 Self-Executing Anonymous Function 으로 알려진 디자인 패턴이고 크게 두 부분으로 구성된다.

첫 번째는 괄호((), Grouping Operator)로 둘러싸인 익명함수(Anonymous Function)이다.
이는 전역 스코프에 불필요한 변수를 추가해서 오염시키는 것을 방지할 수 있을 뿐 아니라 
IIFE 내부의 변수에 접근하지 못하도록 막을 수 있는 방법이다.

두 번째 부분은 즉시 실행 함수를 생성하는 괄호()이다. 이를 통해 자바스크립트 엔진은 함수를 즉시 해석해서 실행한다.
