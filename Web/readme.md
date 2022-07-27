# smarty

스마티란? php와 함께 사용하는 템플릿 엔진입니다. php와는 다르게, 컴파일방식을 사용하며 웹 개발에 있어 생산성을 높이고 코드의 유지 보수를 위해서 필수적으로 사용됩니다.

주로, 템플릿(tpl)과 php파일을 나누는데 사용됩니다. 템플릿은 프론트 php는 백엔드로 이해하면 좋습니다.

스마티의 특징은, 웹 코드를 짤 때 html 코드 안에서 반복문과 같은 기능들을 사용할 수 있다는 겁니다.

스마티를 사용하지 않는다면, 우리는 보통 script를 통해 반복을 하곤 하지만, 스마티를 사용하면 조금 더 편하게 반복이 가능합니다.

```
01 <html>
02
03 <head>
04         <title></title>
05 </head>
06
07 <body>
08         <table>
09                 <tr>
10                         <td>번호</td>
11                         <td>제목</td>
12                         <td>이름</td>
13                         <td>날짜</td>
14                         <td>조회수</td>
15                 </tr>
16         {foreach from=aContents item=item}
17                 <tr>
18                         <td>{$item.id}</td>
19                         <td>{$item.title}</td>
20                         <td>{$item.name}</td>
21                         <td>{$item.date}</td>
22                         <td>{$item.hit}</td>
23                 </tr>
24         {/foreach}
25         </table>
26 </body>
27
28 </html>
```

실제 사용 예제입니다.테이블 안에서, 반복되는 데이터들을 출력합니다.

사용되는 문법 중 쓸만하고 많이 사용할 법한 문법들을 추렸습니다.

1. section

반복문입니다.
```
{{ section name=foo start=1 loop=$loopNum step=1 }}
<html...>
{{ /section }}

```

의 형식으로 사용되며, html 태그 안의 내용을 반복해줍니다.

2. foreach

가장 좋은 문법입니다. 아주 쓸모있습니다.

https://www.smarty.net/

스마티의 공식 사이트입니다. document는 괜찮게 정리되어 있다고 하는데, 잘 모르겠습니다.

from은 반복이 되는 배열, item은 변수의 이름, key도 변수의 이름, name은 foreach의 문법입니다.

```
{foreach key=key item=item from=$smarty.foreach.outer}
<html...>
{/foreach}
```

로 사용됩니다.

