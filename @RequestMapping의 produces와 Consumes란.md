## [Spring] @RequestMapping의 produces와 Consumes란?

> PC 카카오톡을 스프링으로 구현하며 API를 만들던 중 단순 데이터가 아닌 이미지를 넘겨줘야하는 상황에 마주치게 되었다. 
>
> 평소 관성적으로 @RequestMapping 부분에 `{MediaType.APPLICATION_JSON_VALUE}`를 사용해왔지만 json 형태가 아닌 데이터를 넘겨주어야 하는 상황에는 어찌해야할지 몰라 한참을 헤맸다..
>
> 결론적으로 몇 시간의 삽질 끝에 `{MediaType.IMAGE_JPEG_VALUE}`로 바꿔주어 문제를 해결할 수 있었고 계속된 구글링을 하면서 마주친`produces`와`consumes`의 용법이 무엇인지 알고 또 추후에 같은 삽질을 하지 않기 위해.. 공부한 내용을 기록으로 남긴다.

![이미지 불러오기](C:\Users\jungh\Downloads\imageReturn.png)

(이미지 불러오기 성공..)



* @Consumes : 수신 하고자하는 데이터 포맷을 정의
* @Produces : 출력하고자 하는 데이터 포맷을 정의



> @Mapping에서는 `produces`와 `consumes`가 존재하는데 이것은 쉽게 이야기하여 





