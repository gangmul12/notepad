160604
신호 기본 수업(우리학교의 경우 Signal And System)을 수강하다 보면 그럴듯한 정리로 처음 등장하는 것이 바로  Nyquist's Sampling Theorem이라 할 수 있을 것이다.
Nyquist's Sampling Theorem의 기본 골자라고 하면, BW B로 Bandlimited 되어있는 continuous signal을 f_s > 2B로 샘플링하여 disrete signal로 바꾸면 앨리어싱 없이 신호를 다시 continuous signal로 복원할 수 있다는 것이다.
이 때 f_n = 2B를 Nyquist Rate 라고 정의하고, 관련 내용에서 자주 쓴다. 
이런 Nyquist's Sampling Thm은 타임 도메인에서만 살피면 매우 신기하지만, 푸리에 트랜스폼과 f domain의 성격만 잘 이해하고 있다면 얼치기라도 그림만 보고 이해가능하다. 수학적인 유도도 그렇게 헤비하지 않다.
샘플링정리에 대한 내용을 언급하려고 하는 것은 아니니 자세한 내용은 뛰어넘어간다.

이후 통신 관련된 수업을 듣거나, 데이터네트워킹 강좌에서 잠시 나오는 식을 살피다 보면, 우리는 Nyquist Rate를 다시 만날 수 있는데, 이 때도 여전히 f_n = 2B이다. 
하지만 통신이나 데이터 네트워킹 강좌에서 사용하는 신호는 (데이터라는 말에서도 알 수 있듯이) 더 이상 아날로그 신호가 아니기 때문에, 저런 맥락에서 나오는 f_n은 샘플링과 관련된 값이 아니다.
이 맥락에서 Nyquist rate은, BW B로 bandlimited 된 채널에서 보낼 수 있는 최대 symbol rate를 의미한다. 
이에 대한 설명은 통신 입문 책에 설명이 되어있긴 하지만, Nyquist rate이라는 이름을 강조하고 있지는 않아 careless한 강의자가 가르칠 경우 학습자는 영영 sampling thm의 Nyquist rate와 이 Nyquist rate을 구분하지 못하고 강좌를 마칠 가능성이 높다.
또한, Sampling Thm의 증명은 그래피컬하고 쉬운 부분이 있어 인터넷에서 여러 웹페이지와 글과 pdf와 ppt들이 돌아다니지만, 디지털 통신 맥락에서의 수학적 증명은 더러운 수식들의 연속이어서 상대적으로 인터넷에서 궁금증을 해결하기 힘들다.
그래서 정리하는 겸 이 글을 작성한다.

BW B로 bandlimited 되어있는 채널 특성이 ideal lowpass filter형태로 되어있다고 가정을 하면, 대충 만든 symbol의 경우 채널에 의해 모양이 많이 변하게 된다. 
특히 symbol duration이 T라고 한다면 당연히 우리의 상상에서는 symbol이 t=0에서 시작해서 t=T 내에 종결된다고 생각하는데, 저런 채널을 통과할 경우 symbol이 자신의 나와바리를 벗어나 옆으로 살살 새게 된다.
그럴 경우 자신의 옆에 있던 symbol을 침범하게 되고, 이러한 것을 보고 ISI(Inter Symbol Interference)가 생겼다고 한다.
그래서 채널에 전혀 노이즈가 껴있지 않은 상황에서도, bandlimited 되어있다는 이유만으로 심볼이 깨지기 시작한다.
디지털 통신에서 말하는 Nyquist Rate는 결국 noiseless channel 상황에서 심볼이 깨지지 않는 최대 symbol rate를 일컫게 된다.

