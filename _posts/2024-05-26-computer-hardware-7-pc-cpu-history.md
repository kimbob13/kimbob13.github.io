---
title: 컴퓨터 하드웨어 - 7. PC CPU의 역사 (번외편)
date: 2024-05-26 20:40:00 +0900
author: kimbob13
categories: [컴퓨터, 하드웨어]
tags: [computer, hardware, cpu]
media_subpath: /assets/img/2024-05-26/computer-hardware-7-pc-cpu-history
math: true
---

# 개요

이번 글은 번외편으로 PC CPU의 역사를 제가 아는 선에서 간략하게 정리해보고자 합니다. PC CPU의 역사는 크게 두 줄기로 바라볼 수 있는데, 하나는 ISA의 명칭의 변천이 있고 다른 하나는 소비자용 CPU 제품의 경쟁 역사가 있습니다. 먼저 ISA의 역사를 살펴보고 이후 좀 더 복잡한 CPU 제품의 경쟁 역사를 다뤄보도록 하겠습니다.

## 1. ISA의 역사

### 1.1. x86

현재 PC CPU가 사용하는 ISA의 이름은 이미 앞선 CPU 내용에서 언급했듯 **AMD64** 또는 [**x86-64**](https://en.wikipedia.org/wiki/X86-64) 라고 부릅니다. 이것 말고도 같은 아키텍처를 가리키는 여러가지 명칭이 있는데, 여기에 나름 복잡한 역사가 있어 이를 다뤄보고자 합니다.

전통적으로 PC CPU의 아키텍처는 [**x86**](https://en.wikipedia.org/wiki/X86)이라는 이름으로 불렸습니다. 이는 7-80년대 인텔이 내놨던 CPU 제품 이름들이 **8086, 80186, 80286**와 같은 이름을 가지고 있었기 때문입니다. 이후 IBM PC가 인텔의 CPU를 사용하면서 자연스레 **PC CPU의 아키텍처 = x86** 이라는 명칭이 자리잡게 된 것입니다.

다만 현대에 와서 **x86**이라고 하면 주로 32비트 CPU를 의미하는데, 첫 32비트 CPU는 [**인텔 80386**](https://en.wikipedia.org/wiki/X86) 이었습니다. 이전에 나온 시리즈들은 같은 x86으로 끝났어도 16비트 CPU였는데, 32비트 CPU는 이들의 명령어를 확장하여 하위 호환성이 있었습니다. 더군다나 이전 16비트 CPU들은 2000년대가 시작하던 시기만 해도 이미 구시대의 유물이었기 때문에 자연스레 x86이 32비트 아키텍처의 관습적인 명칭으로 자리잡게 되었습니다.

![](intel-i386DX.jpg){: w="300"}
_32비트 PC CPU의 시작을 알린 인텔 80386_

아무튼 1980년대까지만 해도 PC CPU의 핵심 제조사는 인텔이었고 AMD는 인텔 CPU의 클론을 제작하는 업체였습니다[^1]. 즉 당시까지만 해도 AMD는 인텔처럼 **자체적인 마이크로아키텍처**를 설계하지 않았다는 것입니다. 하지만 1990년대부터 AMD도 자체적인 마이크로아키텍처를 설계하며 인텔과는 독자적인 노선을 걷기 시작합니다.

### 1.2. 64비트 CPU - 인텔 아이태니엄

90년대까지만 해도 일반 사용자용으로는 32비트 아키텍처도 충분한 성능을 보이는 데 무리는 없었습니다. 하지만 서버를 필두로 한 기업용 시장은 사정이 조금 달랐으며, 성능 이외에도 32비트 아키텍처는 기본적으로 최대 4GB의 메모리만 사용할 수 있다는 큰 제약이 있었습니다[^2]. 따라서 미래를 본다면 32비트보다 더 발전된 아키텍처가 필요했고, 인텔과 AMD는 각자의 생각을 가지고 **64비트** CPU 개발을 시작하게 됩니다.
 
여기서 인텔은 기존 32비트 아키텍처와의 호환성을 **완전히 버리고** 아예 새로운 64비트 아키텍처를 만들고자 하였습니다. 결론을 살짝 스포하자면 결국 인텔의 시도는 실패하고 AMD의 방식이 성공을 하게 되는데, 사실 인텔이 이렇게 완전히 새로운 아키텍처를 만들고자 한 데에도 나름의 이유는 있었습니다.

앞서 얘기했든 32비트 아키텍처는 32비트가 아니던 시절, 즉 16비트 아키텍처와도 호환되도록 확장해서 만든 아키텍처라 이미 2000년대 초반만 해도 20년이 넘는 역사를 가지는 아키텍처였습니다. 게다가 이들 아키텍처는 모두 인텔이 직접 설계를 했으니 이들이 가지고 있는 구조적인 한계도 잘 이해하고 있었을 것입니다. 따라서 인텔은 레거시를 유지하느니 **완전히 새로운 설계**를 도입하는 꿈을 꾸게 된 것입니다.

그렇게 해서 인텔은 [**IA-64**](https://en.wikipedia.org/wiki/IA-64)라고 하는 새로운 64비트 ISA를 발표하게 됩니다. 그리고 이 ISA를 통해 실제 제품도 나오긴 했는데 [**인텔 아이태니엄 (Itanium)**](https://en.wikipedia.org/wiki/Itanium)이라고 하는 것이 바로 그것입니다.

![](intel-itanium.webp){: w="300"}
_인텔 아이태니엄 CPU_

그렇지만 ISA가 바뀌면 바로 **기존에 잘 돌아가던 프로그램이 전부 무용지물**이 된다는 문제가 있었습니다. 즉 새로운 ISA 용으로 컴파일러도 다시 만들어야 하고, 이를 위해 프로그램의 컴파일도 다시 필요하게 됩니다. 그래서 아키텍처가 변하는 시점에는 이 전환이 매끄럽도록 CPU 제조사의 지원도 빠르게 이루어지는 것이 중요하게 됩니다. 아니면 해당 플랫폼을 쓸 수 밖에 없게 만드는 어떠한 강력한 장점이 있는 것도 좋을 것입니다.

이러한 아키텍처 전환을 성공적으로 해낸 사례를 꼽자면 단연 Apple이 있을 것입니다. Apple의 경우 2020년대에 들어 Mac 시리즈에서도 PC CPU와 작별을 고하고 ARM 기반 자체 아키텍처로 [**Apple Silicon**](https://en.wikipedia.org/wiki/Apple_silicon) 시리즈를 내놓고 있는 것은 잘 알려진 사실일 것입니다. Apple M1을 시작으로 한 이 CPU들은 성능상으로도 꽤나 준수할 뿐더러 무엇보다 이미 수십년간 iOS와 macOS를 통해 쌓아놓은 견고한 플랫폼이 있었기 때문에 이러한 전환이 극초기의 몇몇 잡음을 제하고는 성공적으로 이루어졌습니다.

하지만 인텔 아이태니엄은 그러한 플랫폼적인 강점이 있던 것도 아니었고, 그렇다고 컴파일러와 같은 소프트웨어 지원이 빨랐던 것도 아니었으며, 실제 구현된 CPU의 성능도 인상적이지 못한 데다, 설상가상으로 원래 로드맵보다 훨씬 지연되어 개발이 되었습니다. 그러니 자연히 시장은 원래 프로그램이 제대로 돌아가지도 않으면서 어떻게든 돌아가게 만들어도 딱히 성능도 좋지도 않으니 이를 외면하게 되었습니다.

따라서 시장은 후술할 AMD의 64비트 아키텍처를 선택하게 되었고, 인텔도 울며 겨자먹기로 AMD의 아키텍처를 쓰게 되었으며, IA-64를 기반으로 한 아이태니엄 시리즈는 2021년을 끝으로 완전히 세상에서 사라지게 되었습니다[^3]. (그래도 2021년까지 생산이 되었던 게 개인적으로는 놀랍다면 놀라운 부분이네요)

### 1.3. 64비트 CPU - AMD64

반대로 AMD는 기존 x86 아키텍처와 호환되는 방식으로 64비트 CPU 시대를 열고자 하였습니다. 당연히 이로 인한 장단점은 계속 설명드렸듯 아이태니엄의 장단점과 정확히 상반될 것이니 굳이 더 적지는 않겠습니다.

대신 이 당시의 역사를 조금 더 다뤄보면, 이때 인텔과 AMD는 서로 CPU 클럭수로 치열한 경쟁을 펼치고 있었습니다. 지금에서야 CPU 클럭이 전부가 아니라는 것을 조금만 찾아보면 알 수 있지만, 당시는 소비자용 CPU는 지금처럼 멀티코어화 되어 있지 않았을 뿐더러, 이런 정보를 쉽게 찾아보기 힘든 시대였기 때문에 클럭이 가지는 상징성이 훨씬 컸다고 할 수 있겠습니다.

이런 상황에서 업계 후발주자로만 여겨졌던 AMD가 먼저[**애슬론 (Athlon)**](https://en.wikipedia.org/wiki/Athlon)이라는 제품으로 1GHz의 벽을 넘는 데 성공하게 됩니다[^4]. 이는 인텔에게 꽤 큰 충격을 선사하였고 이에 따라 다시는 클럭 경쟁에 지지 않고자 2000년대 신제품을 클럭에만 집중한 제품을 만들고자 하였습니다.

![](amd-thunderbird.jpg){: w="300"}
_세계 최초로 1GHz를 돌파한 소비자용 CPU인 AMD 애슬론 썬더버드 (Thunderbird)_

즉 지금까지 얘기한 내용을 정리하여 2000년대 초반의 인텔 상황을 다시 한번 정리해보면 아래와 같은 투트랙 전략이 있었다고 볼 수 있겠습니다.
- 64비트 아키텍처: 기존 x86과 **전혀 호환되지 않는** 새로운 IA-64 아키텍처 개발
- 소비자용 CPU: 다른 거 다 필요 없고 **클럭에만 집중한** 마이크로 아키텍처 개발

하지만 이미 IA-64는 2000년대 당시에도 암울한 미래가 엿보이는 상황이었으며, 클럭에만 집중한 제품이었던 **[펜티엄 4](https://en.wikipedia.org/wiki/Pentium_4)** 시리즈 또한 **클럭을 올리는 데**는 성공했지만 **클럭 당 성능**은 오히려 전작인 펜티엄 3보다도 후퇴해버리면서 초창기에는 신제품이 전작보다도 안좋은 성능을 보이기도 했습니다. 당연히 AMD와 경쟁할 수준의 성능은 절대 아니었기 때문에 당시 인텔이 꿈꿨던 두가지 전략은 **모두 처절하게 실패**하게 됩니다.

그러니 AMD로서는 시장이 AMD64를 채택한 것과 더불어 2000년대 초중반, 지금도 회자되는 최고 전성기를 맞게 됩니다. 이에 인텔도 AMD64 아키텍처로 라이센스 비용을 지불해가며 64비트 CPU를 만드는 것으로 선회할 수 밖에 없게 되었습니다.

### 1.4. AMD64의 다양한 명칭

그렇지만 인텔도 시장의 선도자였고 나름 자존심이 강한 회사기 때문에 AMD가 64비트 시장을 선정했다는 것을 숨기고 싶었을 것입니다. 그에 따라 이 아키텍처를 나타내는 다양한 이름이 아래와 같이 등장하게 됩니다.

- **x86-64**: 사실 AMD가 **처음** 64비트 아키텍처를 발표하면서 사용한 이름. AMD64는 이후 후술할 이유로 나오게 됩니다
- **x64**: 위 이름을 줄여서 말한 것 (개인적인 의견인데 자세한 설명을 찾지는 못했습니다). 현재는 플랫폼 가리지 않고 64비트 아키텍처를 나타내는 명칭으로 흔히 사용합니다.
- **IA-32e**: 64비트가 기존 x86 아키텍처인 IA-32를 확장한 것이라고 주장하며 **인텔**에서 사용한 이름
- **EMT64T**: 메모리 주소로 64비트를 사용할 수 있는 기술이라 하여 마찬가지로 **인텔**에서 사용한 이름
- **Intel64**: 굳이 더 설명이 필요하지 않을 것 같습니다.

특히 아래 3개 이름을 보면 아시겠지만 인텔은 노골적으로 AMD의 흔적을 지우려고 했고, 이에 보다 못한 AMD가 자사의 기술임을 강조하기 위해 이후에 정식 명칭을 **AMD64**라는 명칭으로 바꾸게 된 것입니다.

그래서 리눅스 시스템을 많이 다뤄본 분들은 아시겠지만 리눅스에서는 64비트 PC 아키텍처를 대부분 AMD64라는 이름으로 보여줍니다. 윈도우 또한 시스템 환경변수로 프로세서 아키텍처를 AMD64로 보여주기 때문에 간혹 인텔을 쓰는 경우에는 혼동을 하는 경우도 생깁니다.

![](linux-uname-amd64.png){: w="700"}
_Linux 시스템에서 보여주는 아키텍처 이름_

![](windows-env-amd64.png){: w="400"}
_Windows 환경변수에서 보여주는 아키텍처 이름 (인텔 CPU를 사용하는 시스템에서 캡처)_

## 2. 마이크로아키텍처의 역사

> PC CPU의 마이크로아키텍처를 매우 상세히 다룬 국내의 컨텐츠가 있습니다.<br>
> 닥터몰라님의 **CPU WARS**를 참조하시면 PC CPU의 마이크로아키텍처의 변천과 더불어<br>
> 마이크로아키텍처 각각의 구체적인 구현 방식을 확인할 수 있습니다.<br>
> [보러 가기](https://drmola.com/index.php?mid=pc_column&page=13&document_srl=127378)
{: .prompt-tip }

다음으로는 인텔과 AMD가 개발했던 마이크로아키텍처들을 역사적으로 의미있었던 것들을 위주로 시대별로 정리해보겠습니다. 다만 너무 과거의 아키텍처들 (2000년대 이전)은 지금에 와선 많이 낯설기도 할 것이고 (사실 2010년대 이전만 해도 그럴 것 같기는 하지만..), 무엇보다 제가 태어나기 이전의 것들이라(...) 여기서는 생략할 것입니다.

### 2.1. 2000년 전반

이 시기는 앞서 ISA 파트에서도 다뤘듯 인텔은 클럭에만 집중한 시기이고, AMD는 첫 1GHz CPU는 물론이고 AMD64까지 겹쳐서 승승장구하던 시기였습니다. 당시 인텔과 AMD가 개발하던 대표 아키텍처는 다음과 같습니다.

- 인텔: [넷버스트(NetBurst) 아키텍처](https://en.wikipedia.org/wiki/NetBurst) - 펜티엄4 제품군에 적용
- AMD: [K8 아키텍처](https://en.wikipedia.org/wiki/AMD_K8) - 애슬론 64 제품군에 적용

펜티엄4 제품군은 초창기에 (코드네임 윌라멧)는 1GHz가 훌쩍 넘어 2GHz에 달하기도 했으나 클럭 당 성능이 전작 펜티엄3보다 크게 퇴보해서 성능 차이가 거의 없거나 일부 저성능 제품군은 오히려 퇴보까지 했을 정도였습니다. 다만 이후 공정 개선과 일부 설계 개선에 힘입어 나온 코드네임 노스우드와 프레스핫은 클럭을 훨씬 크게 끌어올려 3GHz에 육박하게 되면서 성능은 많이 개선하게 됩니다. 하지만 근본적인 아키텍처의 한계로 경쟁사의 애슬론과는 차이가 꽤 큰 편이었습니다.

이 시기 AMD의 애슬론 제품군은 초창기 K7 아키텍처를 기반으로한 애슬론 XP와 2003년에 나온 K8 아키텍처로 AMD의 첫 64비트 아키텍처 CPU인 애슬론 64 시리즈가 주력이었습니다. 앞서 계속 언급했듯 경쟁사의 신작은 경쟁사의 전작과 경쟁(...)하는 처지였기 때문에 인텔의 점유율을 많이 뺏어오는데 성공하며 최고 전성기를 구가하게 됩니다. 거기에 듀얼코어 시대가 시작되며 나온 애슬론 64 X2도 경쟁사의 펜티엄 D 대비 구조적인 이점으로 훨씬 나은 성능을 보이며 일종의 피크를 찍게 됩니다.

### 2.2. 2000년 후반

하지만 인텔도 가만 있을 회사는 아니기 때문에 2005년 이후 넷버스트 아키텍처를 버리고 다시 새로운 아키텍처를 개발하게 됩니다. 이 시기 인텔은 과거 펜티엄3 시절에 쓰였던 [P6 아키텍처](https://en.wikipedia.org/wiki/P6_(microarchitecture))를 대폭 개량하여 만들었습니다. AMD는 계속해서 K8 아키텍처를 개선하여 내놨으며 이에 따라 이 시기 각 사의 대표 아키텍처는 다음과 같습니다.

- 인텔: [코어(Core) 아키텍처](https://en.wikipedia.org/wiki/Intel_Core_(microarchitecture)) - 인텔 코어, 코어2 시리즈에 적용
- AMD: [K10 아키텍처](https://en.wikipedia.org/wiki/AMD_10h) - AMD 페넘, 페넘2 시리즈에 적용

인텔의 코어 아키텍처는 완벽한 반격이라 할 수 있을 정도로 CPU 시장에 새로운 센세이션을 불러일으켰습니다. 이를 통해 완전히 재설계 되어 나온 듀얼코어 CPU였던 **인텔 코어2 듀오** 시리즈는 진정한 의미의 듀얼코어라 할 수 있는 것에 더해 클럭 당 성능과 전성비가 압도적으로 개선되어 다시 시장 점유율을 대폭 뺏는 데 성공합니다. 여기에 이후 코어2 듀오의 듀얼코어를 두개 이어붙여 쿼드코어로 만든 코어2 쿼드가 또 오버클럭이 매우 잘돼서 일부 매니아에게 사랑받게 됩니다. 특히 이 중에서 코드네임 켄츠필드라 불리는 제품군이 유명한데, 높은 오버클럭 잠재력으로 오랜기간 준수한 성능으로 쓸 수 있었기 때문에 지금도 관련 커뮤니티에서는 **켄츠할배**라고 회자될 정도입니다. (물론 2024년 기준에선 제대로 쓰기 힘든 성능입니다)

반면 AMD는 듀얼코어에 더해 쿼드코어 CPU도 인텔처럼 듀얼코어를 2개 이어 붙인 것이 아닌, 진정한 의미의 쿼드코어 CPU를 개발하겠다고 공표한 상태였습니다. 하지만 개발 진척이 생각대로 되지 않았고 코어2 듀오와 경쟁했어야 할 **페넘 시리즈**도 성능 열세에 밀리게 되어 다시 시장의 외면을 받게 됩니다. 이후 나온 페넘2 시리즈 시절에는 이미 점유율 차이가 꽤 벌어진 상태였으나 그래도 마지막 여명처럼 가격 인하를 통해 가성비를 인정받으며 일부 매니아의 선택을 받기는 했습니다.

### 2.3. 2010년 전반

2010년대 전반과 중반은 그야말로 **인텔 천하**였다고 요약할 수 있습니다. 이 시기를 대표하는 아키텍처는 아래와 같습니다.

- 인텔: [샌디브릿지(Sandy Bridge) 아키텍처](https://en.wikipedia.org/wiki/Sandy_Bridge) - 인텔 코어 i 시리즈 2, 3세대에 적용
- AMD: [불도저(Bulldozer) 아키텍처](https://en.wikipedia.org/wiki/Bulldozer_(microarchitecture)) - AMD FX 시리즈에 적용

사실 2008년 인텔은 새로운 CPU 제품군인 **인텔 코어 i 시리즈**를 발표하며 현재 컴퓨터를 잘 모르는 사람이라도 대부분 들어봤을 **i7, i5** 등의 CPU 제품군을 확립하게 됩니다. 이 i 시리즈의 1세대에 쓰인 아키텍처는 [네할렘(Nehalem) 아키텍처](https://en.wikipedia.org/wiki/Nehalem_(microarchitecture))라는 것으로 이것도 코어 아키텍처 대비 충분히 괜찮은 성능 향상을 보여줬습니다.

![](intel-core-i-1st.jpg)
_인텔 코어 i 시리즈 1세대의 로고_

하지만 이후 2세대 i 시리즈에 사용한 **샌디브릿지** 아키텍처는 시대의 전환점이라 불러도 좋을 정도의 충격을 가져왔습니다. 이는 AMD가 비슷한 시기 내놨던 **불도저** 아키텍처의 성능이 예상보다 **너무 안 좋아서** 어떻게 보면 두가지 충격이 더해져서 이쪽 업계에선 역사적인 사건으로 기록되지 않았나 합니다.

이 시기 AMD의 불도저 아키텍처는 한마디로 AMD를 **불도저로 밀어버릴 뻔한** 아키텍처로 회자되어 AMD가 정말로 망하기 직전까지 내몰리게 됩니다. 이때 나온 CPU는 과거 인텔이 그랬던 것처럼 자사의 전작 제품과 경쟁해야 하는 처지에 놓였으며 CPU보다는 게이밍 콘솔 (플레이스테이션과 XBOX)을 통해 연명하는 신세였다고 할 수 있습니다[^5]. 이렇게 불도저 아키텍처가 처절하게 망한 이유는 인텔이 펜티엄4에서 했던 것처럼 클럭 속도에 집중한 설계 철학을 유사하게 따른 데 더해 멀티코어 성능을 극대화하기로 기대했던 설계 또한 예상처럼 작동하지 않았기 때문이라고 할 수 있습니다.

반면 인텔은 샌디브릿지를 시작으로 완벽히 시장을 장악하며 5년이 넘는 기간 동안 **사실상 독점 체제**를 구축하게 됩니다. 저도 첫 노트북으로 샌디브릿지가 들어간 맥북에어를 사용했었는데 꽤나 오래 사용했을 정도로 성능은 확실했던 기억이 있습니다. 하지만 독점이 너무 오래되니 인텔은 더 이상 **성능 개선의 필요를 느끼지 못했던** 것 같습니다. 쿼드코어가 처음 시장에 등장한 것이 2007년인데 샌디브릿지의 성공으로 무려 2017년까지 10년 간 소비자용 CPU의 최고 등급인 i7 제품군이 쿼드코어에 머물게 됩니다. 물론 아키텍처가 계속 개선되어 클럭 당 성능은 오르긴 했지만 이조차 과거에 비하면 미미한 수준으로 2011년에 나온 2세대 i 시리즈가 2017년까지 그대로 쓰이기에 크게 부족함이 없을 정도였습니다. 그래서 관련 커뮤니티에서는 켄츠할배에 이어 샌디브릿지를 **샌디할배**라고 부르기도 합니다. (그러면서 켄츠할배는 켄츠 고조할배로...)

### 2.4. 2010년 후반

하지만 또 세상에 영원한 강자는 없는 것처럼 AMD 또한 가만히 있지만은 않았습니다. 잠시 얘기를 돌려보면 반도체 업계에서 특히 CPU 설계로 유명한 사람 중 [**짐 켈러(Jim Keller)**](https://en.wikipedia.org/wiki/Jim_Keller_(engineer))라는 사람이 있습니다. 지금 Apple Silicon으로 유명한 Apple SoC의 시작이라 할 수 있는 [Apple A4](https://en.wikipedia.org/wiki/Apple_A4) 개발에도 참여한 적이 있는데, AMD와도 연이 꽤나 깊다고 할 수 있습니다.

![](jin-keller.webp){: w="400"}
_짐 켈러. 2024년 현재는 직접 AI 반도체를 설계하는 회사(Tenstorrent)를 세워서 경영하고 있습니다._

그는 앞서 AMD의 첫 최전성기였던 시절에 사용한 K8 아키텍처와 AMD64 개발에 참여를 했었습니다. 이후 다른 회사들에서도 압도적인 재능을 뽐내다 2012년 경에 다시 AMD에 합류하게 됩니다. 앞서 말씀드렸듯 AMD의 최고 암흑기였던 시절 짐 켈러는 **완전히 새로운 아키텍처** 개발을 지휘하고 3년 후 떠나게 됩니다.

짐 켈러와 함께 또 언급하지 않을 수 없는 인물이 한명 더 있는데 바로 현재 AMD의 CEO인 [**리사 수(Lisa Su)**](https://en.wikipedia.org/wiki/Lisa_Su)라는 인물입니다. 그녀는 대만 출신 미국인으로 전자공학 학사, 석사, 박사를 모두 MIT에서 받은 것만 봐도 이미 범상치 않은 인물임을 알 수 있는데요. 사실 명줄이 거의 끊기기 직전이었던 AMD를 지금의 위치에 있게 만든 것도 바로 그녀입니다.

2012년에 입사한 그녀는, 먼저 앞서 언급한 게이밍 콘솔 분야로 AMD가 연명할 수 있었다고 했는데, 이를 추진한 것이 바로 리사 수입니다. 이때를 기점으로 모든 게이밍 콘솔에 AMD의 칩이 들어가게 되었고 이는 현재까지 계속 이어지며 AMD의 한 사업분야로 당당히 자리잡게 됩니다. 이후 2014년에 AMD의 CEO가 되면서 AMD의 체질 개선은 물론이고 앞서 짐 켈러의 완전히 새로운 아키텍처를 성공적으로 시장에 안착시키며 지금의 AMD가 있게 한 가장 핵심 인물이라 할 수 있습니다.

![](lisa-su.jpg){: w="400"}
_AMD의 CEO인 리사 수._

다시 돌아와서 그렇게 해서 나온 아키텍처와 더불어 2010년대 후반을 대표하는 CPU 아키텍처는 아래와 같습니다.

- 인텔: [커피레이크 아키텍처](https://en.wikipedia.org/wiki/Coffee_Lake) - 인텔 코어 i 시리즈 8, 9세대에 사용
- AMD: [ZEN 아키텍처](https://en.wikipedia.org/wiki/Zen_(first_generation)) - 1, 2세대[^6] 라이젠 시리즈에 사용

이 **ZEN 아키텍처**가 바로 짐 켈러 시절에 완전히 새로 개발한 아키텍처입니다. 2017년에 첫 선을 보이며 클럭 당 성능이 자사 전작 대비 무려 50% 가까이 오를 정도였으며 (물론 전작이 너무 안 좋긴 했죠), 특히 전성비가 압도적으로 개선되어 높은 코어 수도 무리가 없다고 판단하였는지 소비자용 CPU로는 처음으로 **6코어와 8코어 제품**이 처음 등장하게 됩니다. i7과 동급이라 할 수 있는 라이젠 7이 8코어, i5와 동급이라 할 수 있는 라이젠 5가 6코어로 나오면서 가격은 차이가 없었기 때문에 또 다시 CPU 시장에 충격을 주게 됩니다.

이에 인텔도 원래 계획이었다는 말도 있긴 하지만 다소 급하게 코어 i 시리즈 8세대를 출시하며 i7과 i5를 6코어로 늘리게 됩니다. 급기야 2018년에는 i 시리즈 9세대를 통해 **i9**이라는 새로운 제품군을 신설하였고 i9, i7을 각각 8코어까지 늘리게 됩니다. 그렇지만 이 인텔의 노력(?)에 다시 찬물을 끼얹는 사태가 발생하는데 바로 지금도 간간히 회자되는 [**멜트다운(Meltdown)**](https://meltdownattack.com/) 이라는 취약점이 발견된 것입니다.

![](meltdown.png){: h="400"}
_멜트다운 버그_

이 보안 취약점은 90년대 후반 이후로 나온 **모든 인텔 CPU**에 영향을 미치는 취약점이었기 때문에 생각보다 컴퓨터 업계에 가져온 충격이 어마어마했습니다. 즉 20년 간 인텔이 발표한 모든 CPU (당연히 최신 세대까지)에 하드웨어 수준의 취약점이 존재했다는 것이고, 그렇기 때문에 근본적인 해결은 완전히 새로운 하드웨어 설계일 뿐 소프트웨어적으로는 성능 감소를 감수하고 이를 완화하는 것만이 해결책이었습니다. 반면 AMD CPU는 이 버그로부터 안전했습니다. 다만 이 멜트다운과 함께 제기됐던 **스펙터(Spectre)**라는 취약점도 있고 이는 인텔과 AMD 모두 해당되는 취약점입니다. 다만 구현이 어렵기에 멜트다운에 비해선 **상대적으로** 영향력이 제한적인 면이 있다고 합니다 (물론 뚫리면 여전히 심각한 칩 수준의 취약점인 건 동일)

아무튼 가뜩이나 라이젠 때문에 골치 아팠을 인텔 입장에선 설상가상의 사태가 터진 셈이라 인텔이 2010년대 초중반 가졌던 압도적인 우세가 서서히 무너지기 시작합니다. 그래도 이 시절 인텔 CPU는 전성비도 AMD 대비 열세였고 위의 사태도 있긴 했지만 클럭 만큼은 AMD 대비 꽤 많이 높았기 때문에 성능이 우선인 일부 게이머들은 여전히 인텔을 선호하는 편이 아니었나 합니다. (클럭 당 성능도 AMD 대비 우위에 있었습니다)

하지만 ZEN 아키텍처는 아주 훌륭한 아키텍처적 개선을 보여주긴 했어도 추후 개선의 여지가 없는 것도 아니었고, 무엇보다 **반도체 공정**은 계속해서 발전하고 있었기 때문에 잠재력이 아직 충분히 남아있는 상황이었습니다. 2019년에 차세대로 나온 ZEN2 아키텍처에서는 일부 게이밍 성능이 인텔을 넘지는 못했어도 충분히 대체할만큼의 성능은 되었고[^7] 무엇보다 ZEN2 아키텍처를 기반으로 나온 라이젠 3000번대 시리즈에 일반 사용자용으로는 이례적으로 12코어, 16코어 CPU까지 나오게 되며 절대적인 멀티코어 성능은 이미 인텔을 저 멀리 추월하게 됩니다.

### 2.5. 2020년대부터 지금까지

CPU 시장에서 2020년대의 시작은 과연 AMD와 애플이 알렸다고 해도 과언이 아닐 것 같습니다. 애플은 Apple M1을 시작으로 자사 모든 제품을 자체 칩으로 가겠다고 했으며, AMD는 ZEN2의 차세대 아키텍처인 ZEN3 아키텍처를 통해 인텔을 뛰어넘는 데 완전히 성공하기 때문입니다. 먼저 이 시기 대표 아키텍처는 아래와 같습니다.

- 인텔: [골든 코브(Golden Cove) 아키텍처](https://en.wikipedia.org/wiki/Golden_Cove) - 인텔 코어 12, 13세대에 사용
- AMD: [ZEN3 아키텍처](https://en.wikipedia.org/wiki/Zen_3) - 라이젠 5000번 시리즈에 사용

ZEN3 아키텍처는 2020년 하반기에 발표가 되었습니다. 당시 인텔은 i 시리즈 10세대가 있는 상태였고 i9이 10코어까지 늘어난 상황이었습니다. 다만 반도체 공정 개선이 2017년 이래로 제대로 되질 못해서 2020년 기준으로는 꽤나 구식 공정에서 클럭과 코어 수만 무리하게 늘린 상태였기 때문에 이미 전력 소모와 발열 수준이 AMD와는 상대도 되지 않는 실정이었습니다. 다만 절대적인 게이밍 성능이 AMD 대비 좋은 편이었으니 이걸로 연명하는 상황이었습니다.

하지만 ZEN3 아키텍처를 통해 나온 라이젠 5000번대 시리즈가 이런 인텔에 사실상 KO를 가했다고 볼 수 있습니다. 6코어로 나온 라이젠 5 제품군만으로도 i9을 이길 수 있는 게이밍 성능을 보여줘버렸기 때문입니다. 30만원대 CPU로 6-70만원대 CPU보다 나은 게이밍 성능이 가능한데다, 발열과 전력 소모는 2배를 넘어 3배에 가까운 차이었기 때문에 시장이 이를 선택하지 않을 이유가 없었습니다[^8]. 게이밍이 아니어도 라이젠9 제품군은 여전히 12, 16코어였기 때문에 상대가 되지 않는 상황이었고요.

이로서 2020년과 2021년은 AMD가 다시 과거 전성기와 다름없는, 어쩌면 그때보다도 더 나은 상황을 맞이하며 완벽한 부활에 성공하게 됩니다. 2021년 인텔에서 나온 코어 i 시리즈 11세대는 과거 실패 때처럼 전작보다 일부 퇴보하는 성능을 보여주며 급기야 **모래 낭비**라는 악평까지 듣게 됩니다 (아시다시피 반도체의 핵심 재료인 실리콘이 모래를 통해 만들어지죠).

그래도 인텔은 2021년 후반에 새로운 반도체 공정을 통해 나온 골든 코브 아키텍처와 이를 통해 새로 나온 코어 i 시리즈 12세대가 괜찮은 성능 향상을 보여주며 2022년에는 비등한 경쟁 구도를 갖추는 데 성공합니다. 이 12세대의 가장 큰 특징이라면 PC 시장 CPU에서는 처음으로 고성능 코어와 저성능 코어를 섞는 설계인 **빅-리틀 (Big-Little)** 구조를 채택했다는 점입니다. 인텔에서는 각각 성능 코어, 효율 코어라는 의미로 P(Performance)코어, E(Efficient)코어로 부릅니다. 이를 바탕으로 2024년 현재 i 시리즈 14세대까지 나온 상태입니다.

AMD도 2022년에 ZEN4 아키텍처를 발표한 것에 더불어 게이밍 특화 제품군으로 **3D 캐시**를 적용한 제품을 새로 선보이며 게이밍과 일반 작업 영역 모두 서로 비등한 경쟁을 하고 있습니다. 특히 게이밍에 한정해서는 라이젠의 3D 캐시 제품들이 (5800X3D, 7800X3D) 인텔 최고 제품에 비해서도 더 나은 성능을 보여준다는 평이 우세할 정도입니다.

다만 2024년 들어 인텔의 i7, i9 제품군 위주로 너무 과도한 클럭으로 인한 CPU 사망 사례가 큰 문제로 보고되고 있는데요[^9][^10], 이에 따라 12, 13세대로 어느 정도 인텔로 돌아섰던 민심이 다시 이탈하고 있는 상황입니다.

## 정리

이번 글은 컴퓨터 공부에 별 도움은 안되겠지만 저 개인적으로 역사를 살펴보는 것을 좋아해서 나름대로 정리를 해봤습니다. 물론 못 다한 이야기도 있는 것 같고 다른 분들이 중요하다고 생각하는 부분이 일부 빠졌을 수도 있습니다. 그리고 지극히 개인적인 부분이긴 한데 아무래도 첫 데스크탑 조립을 한창 라이젠이 등장하던 시기에 라이젠으로 하기도 했고, 지금까지도 라이젠을 쓰고 있기 때문에 (업글도 몇번 했고) 어느 정도 AMD에 우호적으로 기술한 면이 있지 않을까 합니다. (그래도 노트북은 인텔 CPU...)

물론 그럼에도 최대한 편견 없이(?) 인텔과 AMD의 행보를 다뤄보고자 나름대로 노력하기는 했으며 사실 이런 거에 과몰입하는 것에 큰 의미가 있나라고 생각은 합니다. <strike>(AMD 주주만 승자)</strike> 저는 그때그때 가성비 좋고 참신한 것에 좀 더 손이 가는 편이며 아직까지는 AMD가 이런 면에서는 더 나았기에 AMD CPU를 주로 선택했던것 같습니다.

아무튼 마지막으로 이번 글을 써보니 이런저런 일이 있었지 하면서 나름 추억 회상도 되고, 어쨌든 역사적인 큰 줄기를 알고 있는 것은 어느 분야에서든 배경 지식을 이해하는 데 조금이라도 더 도움이 되지 않을까 하며 이번 글을 마치겠습니다.

---

[^1]: <https://en.wikipedia.org/wiki/AMD#Intel_partnership>
[^2]: 사실 x86 아키텍처 CPU에는 [PAE (Physical Address Extension)](https://learn.microsoft.com/en-us/windows/win32/memory/physical-address-extension)라 하여 32비트 시스템에서도 4GB 이상의 메모리를 사용하게 해주는 기능도 있기는 했는데, 과도기적인 기술인 만큼 어느 정도 제약도 있고 일반인 입장에서는 존재 여부를 알기도 힘들었을 것입니다.
[^3]: <https://www.tomshardware.com/news/last-itanium-shipment>
[^4]: <https://www.zdnet.com/article/its-official-amd-hits-1000mhz-first-5000096067>
[^5]: AMD는 2000년대 후반에 그래픽카드 회사였던 ATI를 인수하며 CPU는 인텔과, GPU는 NVIDIA와 경쟁을 해오고 있습니다. 특히 게이밍 콘솔의 양대산맥인 플레이스테이션과 XBOX에 쓰이는 SoC를 모두 AMD가 만든 것으로 사용하고 있습니다.
[^6]: 사실 라이젠 2세대는 ZEN+ 아키텍처라 하여 ZEN을 미세하게 개선된 아키텍처를 사용했지만 큰 차이는 없습니다.
[^7]: 저도 라이젠 2세대를 처음으로 데스크탑을 쓰게 되었지만 (이전에는 노트북만 사용), 사실 라이젠 1, 2세대만 하더라도 멀티코어 성능의 가성비가 좋았을 뿐 절대적인 성능은 인텔 8, 9세대 대비 다소 부족한 점은 있었습니다.
[^8]: 단순히 CPU 가격 차이 뿐만 아니라 고전력, 고발열 CPU를 쓰게 되면 메인보드, 파워 서플라이, 쿨러도 모두 더 비싼 것을 써야 그 성능을 온전히 누릴 수 있습니다. 이런 점을 모두 고려하고 컴퓨터 본체를 구성한다고 하면 실질적으로는 같은 성능인데도 100만원이 넘는 가격 차이가 날 수 있으니 ZEN3가 가져온 파급력이 더 컸던 것입니다.
[^9]: <https://www.xda-developers.com/intel-13th-gen-14th-gen-crashes/>
[^10]: <https://namu.wiki/w/%EC%9D%B8%ED%85%94%20%EC%BD%94%EC%96%B4%20i%20%EC%8B%9C%EB%A6%AC%EC%A6%88/13%EC%84%B8%EB%8C%80#s-4.1>