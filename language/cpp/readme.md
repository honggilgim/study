# cpp string class

string 은 문자열을 다루는 클래스로 cpp STL에서 주로 제공한다. string는 char와는 다르게 문자열의 끝에 '\n' 이 들어가 있지 않으며, 문자열의 길이를 동적으로 변화시킬 수가 있다.

특히 코딩테스트에서 많이 사용되는 클래스이다.

cin, cout로 입출력이 가능하며 getline 함수도 사용이 가능하다.

생성은

string str = "abcdef"와 같은 방식으로 생성된다.

연산자 또한 사용이 가능하다.

+는 연결에, <>== 등 여러 연산자들이 사용이 가능하다.

str1 == str2와 같이 사용이 가능하며, 실제로 코딩테스트 문제를 풀다가 고민을 많이했는데 str == "aaa"와 같은 방식으로도 사용이 가능하다.

at, str[], str.front(), str.back(), str.length(), str.size()등등 여러 맴버함수도 존재한다.

이 중 많이 쓰이는 것은, str[]와 str.length() <- size와 같기에, 앞으로는 size를 써야겠다. vector와 같이 쓰다보면 헷갈린다.

empty(), erase(n,m) <- n에서 시작해서 m개를 지운다. 많이 사용한다.

substr(n,k) <- n서 시작해서 k개의 문자를 부분 문자열로 반환한다. 많이 사용된다.

toupper(c), tolower(c) 가끔 사용된다. 이정도가 있다.

이번 코딩테스트에서, string에 관련하여 헷갈리는 부분이 많아 다시 한번 정리했다.

# cpp vector class

자동으로 메모리가 할당되는 배열이다. 아주 많이 사용되고, 왠만한 코테에는 전부 사용되는 클래스다.

중간에 값을 삽입, 삭제할 수 있지만 많이 일어나면 시간 초과가 뜬다.

vecotr<자료형> 이름; 으로 생성한다.

string class와 같이 외부 클래스에서도 벡터 생성이 가능하다.

많이 사용되는 함수만 정리하자면,

vector 을 v라고 봤을 때,

v[idx];

v.front();

v.back();

v.clear();

v.pop_back();

v.size(); <- string과 length, size 구분해서 썼었는데, 이제는 size로 통일해야겠다.

v.erase(iter) -> iter이 가리키는 원소 제거.

v.empty()

등등이 많이 사용된다.

## cpp vector class 2차원 배열

vector<vector<int>> v;
  vector<int>v2;
  v.pushback(v2);
  
  와 같이, 이차원 백터를 선언하고 그 안에 백터를 넣어주는 방식으로 푸쉬가 가능하다.
  
  v[]v[] 와 같은 형태로 사용이 가능하고,
  
  비어있는 부분을 참조할 경우, 컴파일러가 에러를 잡아내는 것이 아닌, 런타임 오류가 발생한다.
  
  어렵다. 이건 많이 써봐야 익숙해질 모양이다.



## cpp 우선순위 큐
우선순위 큐 : Priority Queue는 Container(데이터를 저장하는 객체)의 한 종류이며 일반 큐와 다르게, 설정된 우선순위에 따라 탑을 유지하고 나온다다. 내부적으로는 힙의 구조를 가진다.

기본 헤더 : #include <queue>

queue 헤더 안에 들어있다.

기본 사용법 또한 큐와 같으며, 맴버함수로도 큐와 비슷하다.

empty, size, top, push, emplace, pop, swap 와 같이 queue에서 사용하는 모든 맴버함수를 사용할 수 있다.

큰 수가 앞으로 오도록 정렬하여, 큰 값이 앞으로 오지만,
priority_queue<자료형, 구현체, 비교연산자> pq;

에서 비교연산자를 잘 활용하면, 작은 값으로 구성된 큐도 만들 수 있다.

대표적으로, 알고리즘 문제풀이에 많이 보이는

priority_queue <int, vector<int>, greater<int> > pq;

가 있고,

이런 식으로 선언하면 작은 값이 앞으로 오는 우선순위 큐가 만들어지게 된다.

또한,

struct cmp {
  bool operator()(int a, int b) {
    return a > b;
  }
};

구조체를 선언하고,

priority_queue <int, vector<int>, cmp> pq;

우선순위 큐를 선언하면 역시 작은 값이 앞으로 오도록 우선순위 큐가 설정된다.

우선순위 큐는 이런 식으로 선언된다.

구조체를 활용해서도 많이 사용되는데, 예를 들어보면

//사용할 구조체
struct s{
  int i;
  char c;
  
  //생성자
  s(int num, char alpha) : i(num), c(alpha) {}
};

구조체를 생성하고,

// 비교를 위한 기준
struct cmp {
  bool operator()(s a, s b) {
    // int형의 값이 같을 경우
    if(a.i == b.i) {
      // char형의 값이 큰 것이 우선하도록한다.
      return a.c < b.c;
    }
    // int형의 값이 작은 것이 우선하도록한다.
    return a.i > b.i;
  }
};

비교를 위한 기준을 만들고,

int main() {
  //우선순위큐를 선언할때 <자료형, 구현체, 비교연산자> 로 선언한다.
  priority_queue <s, vector<s>, cmp> pq;
  
  //생성자를 이용한 구조체 입력
  pq.push(s(3, 'a'));
  pq.push(s(4, 'b'));
  pq.push(s(5, 'y'));
  pq.push(s(3, 'z'));
  pq.push(s(100, 'z'));

  while(!pq.empty()) {
    s temp = pq.top();
    cout << temp.i << " " << temp.c << endl;
    pq.pop();
  }
// 출력결과
// 3 z
// 3 a
// 4 b
// 5 y
// 100 z
  return 0;
}

이렇게 정렬된다. 이건 앞으로 써먹을 일이 있어 보여 이렇게 적어논다.
