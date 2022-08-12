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
