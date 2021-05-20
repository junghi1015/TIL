## [Spring] @RequestMapping의 produces와 Consumes란?

> PC 카카오톡을 스프링으로 구현하며 API를 만들던 중 단순 데이터가 아닌 이미지를 넘겨줘야하는 상황에 마주치게 되었다. 
>
> 평소 관성적으로 @RequestMapping 부분에 `{MediaType.APPLICATION_JSON_VALUE}`를 사용해왔지만 json 형태가 아닌 데이터를 넘겨주어야 하는 상황에는 어찌해야할지 몰라 한참을 헤맸다..
>
> 결론적으로 몇 시간의 삽질 끝에 `{MediaType.IMAGE_JPEG_VALUE}`로 바꿔주어 문제를 해결할 수 있었고 계속된 구글링을 하면서 마주친`produces`와`consumes`의 용법이 무엇인지 알고 또 추후에 같은 삽질을 하지 않기 위해.. 공부한 내용을 기록으로 남긴다.

![이미지 불러오기](https://user-images.githubusercontent.com/69712761/118387040-c72d2780-b656-11eb-8f9e-f077edba020d.png)

(이미지 불러오기 성공..)

---



> 최근의 추세는 요청 URI를 통해 응답할 데이터를 정하는 것이 아니라, 요청시에 `Accept header`를 이용하여 응답 받고자 하는 데이터의 type을 `요청헤더`에 적고, `content-type`이란 헤더를 통해 사용자가 'request Body'에 담은 내용을 알리도록 함



* **@Consumes : 수신하고자하는 데이터 포맷을 정의**
* **@Produces : 출력하고자하는 데이터 포맷을 정의**



@RequestMapping, @GetMappint, @PostMapping 등 어노테이션 속성으로 `consumes`이라는 속성이 존재하며 이 속성을 이용하여 사용자가 **Request Body에 담는 타입을 제한**시킬 수 있다.

![화면 캡처 2021-05-20 201411](https://user-images.githubusercontent.com/69712761/118969624-3d5bc200-b9a8-11eb-84e5-9c5dd152b607.png)

(이런식으로 수신하고자 하는 데이터 타입의 종류를 여러개 선언할 수도 있다.)



@consumes와 마찬가지로 이번에 @Produces는 응답하고자하는 데이터 타입을 제한하기 위해 사용하는 속성이다. 즉, @Mapping의 어노테이션 속성으로 `produces`를 추가하고 데이터 타입을 지정하면 **해당 데이터타입으로만 사용자에게 응답하겠다는 의미이다.**



![화면 캡처 2021-05-20 201714](https://user-images.githubusercontent.com/69712761/118969756-667c5280-b9a8-11eb-95d1-bd7f9ee7d38d.png)

(관성적으로 사용해오던 json형식을 사용하는 것이 아닌 이미지로 응답하고자 produces 속성의 타입을 변경하였더니 앞선 예시처럼 이미지 리턴을 할 수 있었다..)



구글링을 하면 할수록 점점더 깊은 개념속으로 들어가게되어 한번에 모든 것을 정리를 하자니 엄두가 나질않아 최대한 개념별로 나눠서 정리해야될 것 같다...





