---
title: 컴퓨터 하드웨어 - 2. CPU (1편)
date: 2023-08-20 11:50:00 +0900
author: kimbob13
categories: [컴퓨터, 하드웨어]
tags: [computer, hardware, cpu]
img_path: /assets/img/2023-08-20/computer-hardware-2-cpu-1
---

## 개요

이제 본격적으로 PC의 하드웨어를 하나씩 다뤄보도록 하겠습니다.

첫번째는 이제까지 그래왔고 앞으로도 당연히 그럴 수 밖에 없는 컴퓨터의 최고 핵심 부품인 **CPU**입니다. 이미 모두 잘 아시겠지만 CPU는 **Central Processing Unit**의 약자로, 이름 그대로 컴퓨터의 대부분 작업을 처리하기 위해 중심에 위치한 부품입니다. 따라서 컴퓨터 성능을 가장 직접적으로 결정하는 요소라고 할 수 있습니다.

여기서는 PC CPU의 대표적인 두 제조사인 인텔과 AMD를 간략히 소개한 다음에, 기본적인 CPU의 동작 방식과 CPU를 얘기하면 빠질 수 없는 **아키텍처 (Arhcitecture)**와 관련된 내용을 다뤄보도록 하겠습니다.

## 1. 인텔과 AMD

IBM PC 호환기종이 지금의 PC 시장을 형성하게 되면서 **인텔(Intel)** 이 엄청난 성장을 이루었음은 이전 글에서 언급했습니다. 그래서 일반적으로 **PC CPU = 인텔 CPU** 라는 인식까지도 퍼져있다고 할 수 있습니다.

하지만 PC 조립을 위해 CPU를 찾아보면 **AMD** 라는 회사 또한 등장하는데요, 먼저 이 두 회사를 간략히 소개하고 넘어가도록 하겠습니다.

![](intel-13th.jpg){: w="400"}
_인텔 CPU (Core i 시리즈 13세대)_

![](ryzen-7000.jpg){: w="400"}
_AMD CPU (Ryzen 7000 시리즈)_

### 1.1. 인텔

**인텔 (Intel)** 은 1968년에 창업한 회사로 CPU 뿐만 아니라 전반적인 반도체 업계에서도 절대적인 강자로 군림하고 있는 회사입니다. 대부분 사람들은 PC와 노트북에 붙어있는 스티커로도 한번쯤은 보셨을 것입니다. 인텔은 지금도 업계 영향력은 당연히 막강한 수준이긴 하지만, 일반 소비자용 CPU 시장에 한정해서는 AMD의 존재 때문에 **항상** 압도적이라고 보긴 힘듭니다. (물론 전체 점유율은 높긴 합니다만..)

인텔은 1990년대까지는 소비자용 CPU 시장에서도 압도적인 강자였는데, 2000년대 초반에 나름 야심차게 내놨던 **펜티엄 4** 제품군이 경쟁사 AMD 제품 대비 **높은 소비 전력, 높은 발열, 낮은 성능(...)**을 모두 보여주며 입지가 위태로웠던 시절이 있었습니다. 그러나 2006년 이후에 정말 절치부심해서 새로 내놓은 제품이 반격에 성공하고, 2008년에 처음 공개한 코어 i 시리즈가 AMD를 다시금 압도하는 성능을 보여주게 됩니다. 가뜩이나 동시기 AMD 제품이 펜티엄 4처럼 높은 소비 전력, 높은 발열, 낮은 성능을 보여주며 자멸했기에 2010년대 초중반 소비자용 CPU 시장은 인텔 천하가 됩니다.

하지만 2017년에 AMD가 다시금 반격에 나서면서 조금씩 인텔의 점유율을 가져오게 되었고, 2020년대 이후 적어도 소비자용 CPU 시장에서는 인텔이 AMD를 압도한다고 보기 힘들 정도로 AMD가 많은 점유율을 뺏어오는 데 성공합니다. 그리고 2023년 기준 최신 인텔 제품은 성능은 좋은데, AMD 대비 높은 전력 소비와 발열을 보이면서 아직까지는 2010년대 초중반의 저력을 보여주지는 못하고 있는 상황입니다.

### 1.2. AMD
**AMD (Advanced Micro Devices)** 는 일반 소비자들에게는 아무래도 인텔 대비 인지도는 밀리지만, 회사 자체는 1969년에 창업한 회사로서 사실 인텔만큼의 업력을 가진 회사라고 할 수 있습니다. 초창기 AMD는 인텔 CPU와 호환되는 클론 CPU를 만들며 성장했으나, 1990년대 이후 자체적으로 아키텍처를 설계하게 되면서 PC CPU 시장에 있던 수많은 경쟁사들을 물리치고 인텔과 함께 유이하게 남은 PC CPU 제조사가 되었습니다.

2000년대 초반은 AMD의 최전성기 중 하나로 기억되며, 앞서 인텔의 펜티엄 4를 거의 모든면에서 압도하는 상품성을 통해 PC CPU 시장의 점유율을 조금씩 가져오게 됩니다. 하지만 인텔의 반격으로 조금씩 주춤하다가 2010년대 초반, PC 매니아들 사이에서는 안 좋은 쪽으로 엄청 유명해진 **불도저 아키텍처**가 인텔과 전혀 경쟁이 안되는 성능과 상품성을 보여주며 한때 AMD는 실제로 폐업의 위기까지 몰리게 됩니다.

그래도 플레이 스테이션과 XBox 같은 콘솔 게이밍 기기에 CPU와 GPU를 독점 공급하며 호흡기를 붙여놓고 있었고, 2017년에 새로 발표한 **라이젠** 시리즈가 인텔을 압도하는 가성비와 절대적으로도 나쁘지 않은 성능을 보여주며 다시금 경쟁이 가능한 수준으로 올려놓았습니다. 2020년대 이후로는 새로 내놓는 제품이 이전의 인텔 제품을 확실히 앞서기도 하면서 적어도 성능적으로는 대등한 위치에서 경쟁을 하고 있고, 게이밍 특화 CPU도 따로 내놓으면서 새 제품이 나올 때마다 인텔과 어떤 경쟁을 할지 매니아들을 흥미진진하게 만들어주고 있습니다.

## 2. CPU의 작동 방식

> 유튜브의 bRd 3D 님께서 CPU 작동 방식을 영상으로 정리한 훌륭한 컨텐츠가 있습니다.<br>
> 부족한 제 설명이 이해가 잘 안되시면 참고해보시면 좋을 것 같습니다.<br>
> <del>제 설명도 가급적 봐주시면 감사하겠습니다...</del><br>
> [보러 가기](https://www.youtube.com/watch?v=Fg00LN30Ezg)
{: .prompt-tip }

이제 CPU란 도대체 어떤 역할을 어떤 방식으로 수행하는지를 간단히 정리해보도록 하겠습니다.

### 2.1. 컴퓨터의 연산이란

CPU란 컴퓨터의 중앙 연산 장치를 의미하고, **컴퓨터 (Computer)** 란 사전 그대로 해석하면 **계산기**를 의미한다는 건 모두 아실 거라고 생각합니다. 그러면 **무엇**을 계산하기 위해 컴퓨터는 지금과 같은 모습으로 발전하였을까요?

CPU 내부에서 이루어지는 연산은 우리가 수학 시간에 배우는 **사칙 연산**과 더불어 다양한 연산들이 수행됩니다. 정확히 사칙 연산은 주로 **산술 연산 (Arithmetic Operation)** 이라고 부르고, 이외에도 논리 연산, 비트 단위를 움직이는 shift 연산, 메모리 접근을 위한 연산 등이 다양하게 수행됩니다. 더불어서 프로그래밍에서 정말 자주 쓰이는 조건문과 반복문을 위한 분기 연산 등 프로그램 실행에 기초적인 연산 또한 상당수 존재합니다.

![](cpu-operations.png){: w="600"}
_CPU가 수행하는 대표적인 연산들_

### 2.2. 명령어

이제 이 CPU가 **어떻게** 위에서 얘기한 연산을 수행하는지 알아보겠습니다.

컴퓨터 또한 기계이니 사람의 **명령**을 받아 요청받은 동작을 수행하게 됩니다. 그래서 CPU는 각각의 명령을 **명령어 (Instruction)** 단위로 받아서 실행하게 됩니다. 명령어는 CPU 아키텍처 별로 **사전 정의**된 포맷에 따라 이루어진 0과 1의 집합, 즉 비트의 나열입니다. 이 명령어는 기계가 **직접** 해석하는 대상이기 때문에 흔히 **기계어**라는 이름으로도 불립니다.

프로그래밍을 접해보신 분들이면 알겠지만 현존하는 대부분 프로그래밍 언어는 **컴파일러** 혹은 **인터프리터**를 통해 기계어(즉 명령어)로 번역하는 과정이 필요합니다. 이들을 사용한 컴파일 과정이 바로 코드를 기계어로 번역하는 과정이라고 할 수 있습니다.

![](compiler.png){: w="700"}
_컴파일러의 역할 ([출처](https://velog.io/@golmori/%EC%BB%B4%ED%8C%8C%EC%9D%BC%EB%9F%AC-%EC%9D%B8%ED%84%B0%ED%94%84%EB%A6%AC%ED%84%B0))_


아래 그림은 PC CPU 아키텍처 위에서 아래와 같은 1과 2를 더하는 C언어 프로그램을 기계어로 바꾼 모습입니다.
```c
int main(void)
{
    int a, b, c;

    a = 1;
    b = 2;
    c = a + b;

    return 0;
}
```

![](x86-assembly-example.png){: w="600"}
_1 + 2 = 3을 수행하는 프로그램을 명령어 단위로 확인한 예시_

위에서 실제로 `1 + 2 = 3`을 수행하는 부분이 빨간색 상자 안의 명령어입니다. 초록색 상자가 실제 기계어를 16진수로 나태난 부분이고, 주황색 상자는 기계어를 사람이 좀더 보기 편한(?) 형태로 바꾼 **어셈블리 언어 (Assembly Language)** 입니다.

보통 명령어를 얘기할 때는 당연히 문자열로 이루어진 어셈블리 언어를 위주로 얘기하게 됩니다. 어셈블리 언어를 보는 방법은 명령어마다 조금씩 다르지만 `add` 명령어를 보면 `<명령 종류> <레지스터 이름>,<레지스터 이름>` 과 같은 형태로 이루어져 있습니다.

CPU는 이 명령어를 한번에 하나씩 처리하며 연산을 수행하게 됩니다. 이 명령어를 해석해서 처리하는 과정을 **얼마나 빨리** 하는가가 곧 CPU의 성능이라 할 수 있고, CPU 아키텍처는 항상 이를 향상시키는 방향으로 발전되어 왔다고 봐도 무방합니다.

가장 왼쪽의 메모리 주소 부분은 뒤쪽에서 자세히 설명하겠습니다.

### 2.3. 레지스터와 CPU 비트 수

**레지스터 (Register)**는 CPU가 연산을 수행하기 위해 임시로 데이터를 저장하는 CPU 내의 공간을 의미합니다. 명령어를 어셈블리로 표현한 위 예시를 보면 `레지스터 이름` 이라고 말씀드린 `%eax, %edx` 같은 것들이 수없이 많이 등장하는 것을 확인할 수 있습니다.

레지스터의 종류에는 크게 **범용 레지스터 (General Purpose Register)**와 정해진 목적으로 사용되는 다양한 종류의 **전용 레지스터 (Special Purpose Register)**가 있습니다. 범용 레지스터가 몇개 있는지, 전용 레지스터에 어떤 것들이 있는지는 CPU의 아키텍처마다 제각각입니다.

여기서는 PC의 CPU를 주로 살펴볼 것이니 PC가 사용하는 **x86** 아키텍처를 예로 들면, `%eax`, `%edx`와 같은 것들은 범용 레지스터의 이름입니다. 범용 레지스터는 CPU가 연산에 필요한 데이터라면 종류에 상관없이 일반적인 목적으로 사용할 수 있는 레지스터임을 의미합니다. 

반대로 전용 레지스터는 연산 과정에서 꼭 필요한 특정 정보들을 저장하는 용도로 사용되는 레지스터를 의미합니다. 위의 예시에서는 `%rbp`와 `%rsp`가 이런 성격을 가지고 있는데, 사실 이들은 **범용 레지스터처럼 사용할 수도 있어서** 칼로 자르듯이 구분되지는 않습니다.

![](x86-registers.png){: w="500"}
_x86 아키텍처의 레지스터들_

여기서 짚고 넘어갈 부분은 범용 레지스터의 크기입니다. 위 그림을 보면 x86의 경우 하나의 레지스터가 **32비트**의 크기를 가지고 있는 것을 확인할 수 있습니다. 흔히 CPU랑 윈도우를 얘기할 때 **32비트 CPU**다, 이 윈도우는 **64비트 윈도우**다 같은 얘기를 많이 들어보셨을 것입니다. CPU에 붙는 비트 수가 바로 이 **범용 레지스터의 크기**를 의미하고, 윈도우는 해당 비트 수의 CPU를 지원하는 윈도우임을 의미합니다.

![](system-info.png){: w="500"}
_윈도우에서 확인한 시스템 정보 (64비트 예시)_

### 2.4. 폰 노이만 구조

갑자기 챕터 제목이 좀 거창해진 느낌이 있는데, 마지막으로 컴퓨터에서 CPU와 함께 빼놓을 수 없는 **메모리**와 관련된 내용을 얘기하기 위함입니다.

CPU는 데이터를 어디선가 가져와서 처리하고 다시 결과를 어딘가에 저장해야 합니다. 레지스터는 단지 CPU 내에서 사용하는 임시 저장 공간이기 때문에 CPU **외부**에 데이터를 저장하는 공간이 필요합니다. 이 공간을 바로 **메모리 (Memory)** 라고 부릅니다.

![](cpu-memory.png){: w="500"}
_CPU와 메모리_

메모리에는 프로그램이 실행되는데 필요한 데이터도 저장되어 있고, **프로그램 그 자체**도 저장되어 있습니다. 여기서 말하는 프로그램은 위에서 다룬 명령어라고 보시면 됩니다. 중요한 부분은 **프로그램 자체가 저장**되어 있다는 부분인데, 아주 오래전 (1950년대 이전) 컴퓨터는 프로그램이 메모리에 저장된다는 개념이 없었기 때문입니다.

요즘 컴퓨터를 사용하면서 서로 다른 프로그램을 동시에 실행시키는 건 너무나 자연스워서 이게 불가능하다는 것이 잘 와닿지는 않을 것 같습니다. 하지만 과거에 이 개념이 없던 컴퓨터는 다른 프로그램을 실행하려면 **컴퓨터 하드웨어 구조 자체(!)** 가 바뀌어야 했습니다. 지금으로 비유하면 1번 프로그램이 저장된 SSD를 꽂아놓고 쓰다가 2번 프로그램을 쓰려면 본체를 뜯어서 2번 프로그램이 저장된 SSD로 교체한 다음에 다시 실행해야 한다.. 정도의 느낌이 될 것 같습니다.

그렇지만 1945년에 폰 노이만이 **프로그램도 메모리에 저장한다는 개념**을 소개하면서[^1] 컴퓨터는 CPU와 메모리만 갖추고, 서로 다른 프로그램은 메모리 공간에서 **프로그램이 저장된 영역만 바꾸면** 되는 아키텍처를 소개하였습니다. [^2] 이처럼 프로그램 자체가 메모리에 저장되는 개념을 [**저장된 프로그램 개념 (Stored-program concept)**](https://en.wikipedia.org/wiki/Stored-program_computer)이라 부르고 이 개념을 사용한 아키텍처를 [**폰 노이만 구조 (Von Neumann Architecture)**](https://en.wikipedia.org/wiki/Von_Neumann_architecture) 라고 부릅니다.

![](von-neumann-architecture.png){: w="500"}
_폰 노이만 구조 도식도_

앞쪽의 `1 + 2 = 3을 수행하는 프로그램을 명령어 단위로 확인한 예시` 그림에서 가장 왼쪽의 파란색 상자가 메모리 주소를 나타낸다고 해놓고 설명을 따로 하지는 않았습니다. 해당 부분은 방금 소개한 저장된 프로그램 개념을 알고 볼 때 더 이해하기가 쉽기 때문인데, 아마 대부분 감이 오시지 않았을까 합니다.

예로 들었던 `add` 명령어의 경우 기계어 부분을 보면 2바이트의 크기를 가지고 있는 것을 알 수 있습니다 (16진수 4자리는 16비트 = 2바이트). 그리고 주소는 `1141`로 표시되어 있는데 이 주소를 포함하여 2바이트 만큼의 메모리 공간을 차지하고 있는 것입니다. 여기서 메모리 주소는 **바이트** 단위로 되어 있다는 것도 굉장히 기초적이면서 중요한 부분입니다. 그래서 다음 명령어를 보면 `1141`에서 2만큼 더한 `1143`에서 시작합니다.

![](x86-assembly-example.png){: w="600"}
_1 + 2 = 3을 수행하는 프로그램을 명령어 단위로 확인한 예시 (반복)_

정리하면 현존하는 거의 모든 컴퓨터는 이 폰 노이만 구조를 가지고 있다고 할 수 있습니다. PC, 노트북 뿐만 아니라 스마트폰, 태블릿 PC, 다양한 임베디드 기기, 심지어 SSD 같은 PC의 부속품 까지 이 구조로 만들어져 있다고 할 수 있습니다. (SSD도 내부적으로 CPU라 할 수 있는 컨트롤러와 메모리를 가지고 있기 때문입니다)

### 2.5. CPU 명령어 사이클

앞서 다룬 내용들을 모두 종합하여 CPU가 하나의 명령어를 수행하는 과정을 정리하면 아래와 같습니다. 이를 [**명령어 사이클 (Instruction Cycle)**](https://en.wikipedia.org/wiki/Instruction_cycle) 이라고 부릅니다.

1. CPU가 메모리에서 실행할 명령어를 불러옴 **_(Fetch)_**
2. CPU가 명령어를 해석함 **_(Decode)_**
3. 명령어가 연산에 데이터를 필요로 하는 경우 메모리에서 해당 데이터를 불러옴 **_(Load)_**
4. CPU가 불러온 데이터(있다면)를 사용하여 연산을 수행 **_(Execute)_**
5. 연산 결과를 메모리에 저장 **_(Store)_**
6. 1번으로 돌아가서 다음 명령어 반복

![](instruction-cycle.png){: w="400"}
_명령어 사이클 (Load 부분은 빠져있음)_

이 사이클을 아는 것이 CPU 아키텍처를 배우는 데 있어 **첫걸음**이라고 할 수 있습니다. 따라서 이를 숙지하면 앞으로 제가 다룰 내용은 물론이고 관련 내용을 공부할 때도 이해가 좀 더 수월해질 수 있을 것입니다.

## 3. 정리

여기까지 해서 CPU의 간단한 동작 원리와 중요한 키워드들을 알아보았습니다. 원래는 한 포스트에 나머지 ISA나 마이크로아키텍처 같은 이야기도 모두 적으려 했는데, 분량이 역시 의도와는 달리 너무 길어졌네요. 나머지 얘기는 다음 포스트에서 이어서 소개하고자 합니다.

긴 글 읽어주셔서 감사합니다.

> 언제나 그렇지만 오류나 오해의 소지가 있는 내용이 있다면 언제든 알려주시면 감사하겠습니다. <br>
> 최대한 정확한 설명을 지향하지만 설명을 간소화 하다 보니 이상한 부분이 분명 있을 것이라 생각합니다.<br>
{: .prompt-info }

---

[^1]: 엄밀히 말하면 이 개념을 폰 노이만이 소개했다고 보기는 어렵다고 합니다. 폰 노이만의 이름으로 발표된 것은 맞지만, 이 개념 자체를 처음 제시한 것은 [에커트](https://en.wikipedia.org/wiki/J._Presper_Eckert)와 [모클리](https://en.wikipedia.org/wiki/John_Mauchly)라는 사람들이었는데, 발표되는 과정에서 이들의 이름이 누락되는 다소 복잡한 역사가 있습니다. 다음 글들을 참고하시면 좋을 것 같습니다. [영어](https://en.wikipedia.org/wiki/Von_Neumann_architecture#Development_of_the_stored-program_concept), [한국어](https://blog.wishket.com/it%ED%98%81%EB%AA%85%EC%9D%98-%EC%98%81%EC%9B%85%EB%93%A4-%EC%84%B8%EA%B3%84-%EC%B5%9C%EC%B4%88%EC%9D%98-%EB%B2%94%EC%9A%A9-%EC%BB%B4%ED%93%A8%ED%84%B0-%EC%97%90%EB%8B%88%EC%95%85%EC%9D%98-%EA%B0%9C/)
[^2]: <https://en.wikipedia.org/wiki/Von_Neumann_architecture#History>