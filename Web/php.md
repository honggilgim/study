# php 하면서 검색한거 기록해두기

php는 기본적으로, 서버 언어다. js처럼 클라이언트 쪽에서 동작하는 언어가 아니라, 서버에서 동작한다. 주로 하는일은 db와의 소통이라고 생각한다.

## php 변수 선언
```
$s
```

php는 변수를 선언, 다룰 때 모두 $를 사용한다. js처럼 var를 사용하거나 하지 않는다.
## php alert

php는 alert가 안먹는다. 그래서 alert를 사용하려면,

```
echo "<script>alert('클럽 오류');</script>";
```

이런 식으로 동작해주어야 한다.

## php 반복문
```
	for($i=0; $i<count($list_hbook); $i++)
	{
		$hbook = $list_hbook[$i];

		if(empty($hbook->img))
		{
			$list_hbook[$i]->img = "/admin/upload/img/file_d10c88f869301b1238f53cfdff8e9d7c_1659939638.png";
		}
	}

```

(예시)

위 반복문은 count 함수를 이용해 사이즈를 측정하고, 반복문을 돌린 함수다

