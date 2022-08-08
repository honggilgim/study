# php 하면서 검색한거 기록해두기

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

위 반복문은 count 함수를 이용해 사이즈를 측정하고, 반복문을 돌린 함수다.

## php 

