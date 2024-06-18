*해당 웹사이트는 단순히 EO채널을 좋아하는 마음을 담아 만들어졌으며, 어떠한 수익을 얻을 계획도 없습니다.*

## 📌 요약
<table>
    <tr>
        <th>기간</th>
        <td>2024-06-12 ~ 2024-06-18 </td>
    </tr>
    <tr>
        <th>기술 스택</th>
        <td>TypeScript, React, Vite, Supabase, Emotion, i18next</td>
    </tr>
    <tr>
        <th>배포 링크</th>
        <td>https://eo-galaxy.vercel.app/</td>
    </tr>
</table>

## 📢 기획 의도 : 어이 여보시게들, EO 채널 보시라게들
<img width="1096" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/df4e9a60-cd59-44be-812d-c217c53ac525">

<br />

친구와 이야기를 나누던 중...    
종강을 앞둔 **친구 A**는 고민을 토로한다.

```
"곧 있으면 종강인데, 방학 때 놀다가 그냥 방학이 끝나 버릴까봐 걱정이야..."
```

고민을 듣고 있던 **친구 B**는 대답한다.

```
"EO 채널 봐"
```

원래 엄청 재미있는 상황극처럼 기획 의도를 적고 싶었지만, 역량 부족으로 어설프게 적게 되었다.   


하지만 다시 논점으로 돌아가서, 기획 의도에 대해 서술해보자면...    
종강 시즌을 맞이하여, **종강 후 운세를 알려주고 EO 채널 영상들을 소개함으로써 알찬 방학을 보낼 수 있게 도와주는 이벤트성 웹 서비스**를 만들게 되었다. 

## 🧠 핵심 기능 : 어머 이건 꼭 구현해야 해 
<img width="400" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/dbfd0835-c7c9-477a-9cdb-88525e6766d7">

이벤트성이 강한 서비스이다보니, 평소 구현해보고 싶었던 기능 혹은 기술 스택을 사용하여 만들게 되었다.

### 1️⃣ i18next 번역 데이터 관리 사이트
평소 프론트엔드 개발자로서, **팀에 기여할 수 있는 방법에 대해 고민**을 많이 한다.  
처음에는 성능 최적화, 유려한 인터랙션을 통한 유저 확보 정도에 생각이 머물렀다.   
어떻게 하면 프론트엔드 개발자가 팀에 기여할 수 있을지 고민도 하고 주변에 질문도 해 본 결과,    
내가 위에 언급한 역할도 할 수 있지만, 디자인 시스템 등 팀에 코어적인 부분에 기여하여 팀의 개발적인 역량에 보탬이 될 수도 있고   
또는 기획자가 접근해야 할 자료가 있다면 편하게 접근할 수 있는 루트를 만들 수도 있는 것이다.

<img width="700" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/6fa8e216-c4eb-4132-8f26-c08e1308d389">

그래서 해당 생각을 녹여낸 것이, EO Galaxy 프로젝트이다.   
`i18next 써보고 싶어!`라는 마음과, `만약 i18next를 쓰는 회사라면, 어떻게 그 팀에 기여할 수 있을까`라는 고민이 합쳐진 결과물이다.   

다국어 처리를 사용하는 팀이라면, 번역 데이터 관리가 중요한 업무 중 하나일 것이라고 생각했다.   
물론 구글 스프레드시트나 [i18nexus](https://i18nexus.com/)를 사용하는 방법도 있겠지만, 비용 문제 등에서 벗어나기 위해서는 자체 웹 사이트가 있으면 편하겠다라는 생각을 하였다.   
그래서 💡**1)어드민 사이트에서 번역 데이터를 관리하고 2)해당 데이터를 supabase를 통해 3)실제 서비스 페이지가 이용하는 방식**으로 구현하였다.

### 2️⃣ 공유하기 버튼 VS 페이지 이동 버튼
기획, 디자인, 개발 모두 나 혼자 진행하다보니 결정을 내릴 때 고민이 머문 순간들이 종종 있다.  
아래 화면이 대표적인 예시이다.   
이벤트성 웹사이트이기 때문에 `공유하기`는 매우 중요한 기능이라고 생각을 한다.    
하지만 궁극적으로 도달하길 원하는 '홈 페이지'까지의 이동을 맡은 `페이지 이동 버튼` 역시 중요하다고 보았다.   

<div display="flex">
  <img width="315" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/3b717684-2b72-46a1-a4fd-a8ae59e216b2">
  <img width="315" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/61af693f-f8df-43d4-9030-b793763408b9">
</div>

그래서 어떤 UI/UX 선택이 맞는 선택인지를 확인하고자, 두 화면 모두를 구현하였다.   
FE만 있는 프로젝트이고 회원가입을 하지 않기 때문에 유저를 식별할 수 없었다.   
따라서 짝수 시(2, 4, 6시...)에는 공유하기 버튼이 메인인 화면이, 홀수 시(1, 3, 5시...)에는 페이지 이동 버튼이 메인인 화면이 노출되게 하였다.   

```
import { useEffect, useState } from "react";

const useIsEvenTime = () => {
  const [isEvenTime, setIsEvenTime] = useState(new Date().getHours() % 2 === 0);

  useEffect(() => {
    const interval = setInterval(
      () => {
        const currentHour = new Date().getHours();
        setIsEvenTime(currentHour % 2 === 0);
      },
      60 * 60 * 1000,
    );

    return () => clearInterval(interval);
  }, []);

  return isEvenTime;
};

export default useIsEvenTime;
```

이렇게 useIsEvenTime 훅을 만들어서, 짝수 시 혹은 홀수 시를 판별하였다.   
그리고 각 버튼에 구글 태그를 심어 클릭 이벤트를 트랙킹하고자 하였다.   
<img width="384" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/cbe54eb9-286c-4654-87c8-f18cf0b8f5e4">


### 3️⃣ 비눗방울 인터랙션
**평소 인터랙션에 관심이 많아서** [jhey](https://x.com/jh3yy)님의 코드를 자주 구경한다.   
그래서 나도...! 해보고 싶다...! 이런 마음이 있었는데, 마침 [뉴진스 버블검 뮤비](https://www.youtube.com/watch?v=ft70sAYrFyY) 속 비눗방울 모습이 너무 예뻐서, 비눗방울 인터랙션을 만들고 싶었다.   
<div display="flex">
  <img width="200" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/c5a29e21-36ff-434d-949e-1344ecc5e502">
  <img width="200" alt="image" src="https://github.com/EO-galaxy/.github/assets/97885933/95abd5c6-06f9-4d5e-a709-de984d645846">
</div>

![2024-06-184 06 51-ezgif com-video-to-gif-converter](https://github.com/EO-galaxy/.github/assets/97885933/980bf718-a524-4956-8406-6c817ebb10b5)

그 외 프로젝트를 하면서 겪은 트러블슈팅 등은 
[EO-galaxy-FE 이슈 페이지](https://github.com/EO-galaxy/EO-galaxy-FE/issues) &
[EO-galaxy-ADMIN 이슈 페이지](https://github.com/EO-galaxy/EO-galaxy-ADMIN/issues)
에서 확인이 가능하다
