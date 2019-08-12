# 생성자 함수 사용하기
다음 두 단계를 거쳐서 개체를 만들 수도 있습니다.

생성자 함수를 작성함으로써 개체를 정의합니다.
new 키워드를 사용하여 개체의 인스턴스를 만듭니다.
개체 형식을 정의하기 위해서, 개체의 이름, 속성, 메소드를 지정하는 함수를 만듭니다. 자동차를 나타내기 위한 개체를 만들고 싶다고 해봅시다. 그렇다면 이 형식이 car라고 불리길 원할 것이고, make, model, year라는 속성이 있기를 원할 것입니다. 원하는 것을 이루기 위해서 이런 함수를 작성합니다.

<pre><code>
function car(make, model, year) {
   this.make = make;
   this.model = model;
   this.year = year;
}
</pre></code>

함수의 인자로 전달받은 값을 개체의 속성에 할당하기 위해서 this를 사용했다.

이제 우리는 mycar라는 개체를 이렇게 만들 수 있습니다.

<pre><code>
mycar = new car("Eagle", "Talon TSi", 1993);
</pre></code>
이 문장은 mycar를 만들고, 지정된 값을 mycar의 속성에 할당합니다. 그러면 mycar.make는 "Eagle"이라는 문자열 값을 가지고, mycar.year는 1993이라는 정수를 가질 것입니다.

우리는 new를 써서 car 개체를 몇 개라도 만들 수 있습니다.

<pre><code>
kenscar = new car("Nissan", "300ZX", 1992);
vpgscar = new car("Mazda", "Miata", 1990);
</pre></code>
개체는 다른 개체를 속성으로 가질 수 있습니다.예를 들어, person 개체를 다음과 같이 정의했다고 합시다.

<pre><code>
function person(name, age, sex) {
   this.name = name;
   this.age = age;
   this.sex = sex;
}
</pre></code>
그리고나서 person 개체의 인스턴스 두 개를 만듭니다.

<pre><code>
rand = new person("Rand McKinnon", 33, "M");
ken = new person("Ken Jones", 39, "M");
</pre></code>
이제 우리는 car가 owner라는 속성으로 person 개체를 가지도록 car의 정의를 바꿀 수 있습니다.

<pre><code>
function car(make, model, year, owner) {
   this.make = make;
   this.model = model;
   this.year = year;
   this.owner = owner;
}
</pre></code>
새 개체 인스턴스를 만들 때 이렇게 쓸 수 있습니다.

<pre><code>
car1 = new car("Eagle", "Talon TSi", 1993, rand);
car2 = new car("Nissan", "300ZX", 1992, ken);
</pre></code>
위 문장에서 owner 인자로 문자열 상수값이나 정수값을 전달하는 대신 rand와 ken이라는 개체를 전달했다는 사실에 주의하십시오. 이제 car2의 소유자 이름을 알고 싶으면 이런식으로 접근할 수 있습니다.

<pre><code>
car2.owner.name
</pre></code>
정의된 개체에 아무때나 속성을 추가할 수 있다는 사실을 기억하십시오.

<pre><code>
car1.color = "black"
</pre></code>
이 문장은 car1에 color 속성을 추가하고 "black"이라는 값을 할당합니다. 그러나 이 문장이 다른 개체에 영향을 미치지는 않습니다. 같은 형식을 가지는 모든 개체에 새 속성을 추가하고 싶으면 car 개체 형식의 정의에 속성을 추가해야 합니다.
