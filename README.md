# Lab5 Team Activity - Git workflow

팀원 권우석, 박지윤, 우태희, 오승기, 빈현우, 정재준  

---

### 개요  

Vincent Driessen이 2010년 1월 5일 개발 모델에 대하여 적은 글은 수많은 개발자들이  
자신의 프로젝트를 진행하는 데 영향을 끼쳤고, 아직까지도 가장 많이 이용되는  
workflow중 하나이다.  
  
2020년 5월 Vincent Driessen는 자신의 개발 모델에 대한 성찰에서 "모든 프로젝트에  
적용되는 만병통치약은 없으니 자신의 프로젝트 맥락에 맞춰 사용해야 한다."라는 말을 남겼다.  
  
이처럼 10년이 지난 오늘날에도 사랑받고 있는 workflow이기에 원문을 번역하며  
개발 모델을 학습해보기로 했다. 원문은 Git의 장점과 함께 자신의 개발 모델을  
branch를 중심으로 설명한다. branch는 Main branch(master, develop)와  
Supporting branch(Feature, Release, Hotfix)로 나뉘어 총 5개이고 각  
branch의 목적과 사용 방법을 설명하는 방식으로 글이 전개된다.  

---

이 게시물에서는 작년 몇몇 프로젝트(일과 개인적인 프로젝트 모두)에서 소개한 성공적인  
개발 모델을 보여주려 한다. 나는 한동안 이 개발 모델에 대해 글을 쓰고 싶었지만 지금까지  
시간이 허락하지 않았다. 나는 프로젝트의 세부 사항은 생략하고, 단지 branching 전략과   
형상 release 관리에 대해서만 설명할 것이다.

### Why Git?

중앙 집중형 관리 시스템 와 비교했을 때 Git이 가지는 장단점에 대한 치열한 논쟁은 웹을 통해  
확인할 수 있다. 그곳에는 불꽃 튀는 전쟁이 계속해서 일어나고 있다. 개발자로서, 나는 오늘날  
어떤 도구보다 Git을 선호한다. Git은 merging과 branching에 대해 개발자가 생각하는 방식을  
완전히 바꾸었다. 내가 이전에 사용했던 고전적인 CVS/Subversion에서, merging과 branching은  
항상 위험한 것으로 여겨졌고(merge 충돌이 일어나면, 팀원들은 당신을 물어뜯을 것이다!)  
모든 것을 한 번에 진행해야 했었다.  
  
  
> CVS - Concurrent Versions System의 약자로 1980년대 만들어진 형상관리 프로그램이다. 파일 관리나 커밋 중 오류 시 롤백이 되지 않는 등 기술적인 문제가 많아 요즘은 사용되지 않는다.  
  
  
> Subversion - 문제가 있던 CVS를 대체하기 위해 탄생한 형상관리 도구이다. tag와 branchs라는 개념을 지원하여 형상(버전) 관리를 편하게 만들었다.

  


하지만 Git에서는, 이러한 작업들이 굉장히 쉽게 이루어지고 일별 workflow에서 핵심적인 요소 중 하나이다. 예를 들어, CVS/Subversion 교본에서는 branching과 merging은 전문가를 위한 마지막 챕터에서 다루는 주제이지만 Git 교본에서는 3번째 챕터에서 다루는 기본적인 주제이다.

Git의 단순함과 반복적인 특성의 결과로 branching과 merging은 더 이상 두려움의 대상이 아니다. 형상 관리 도구들은 그 무엇보다 branching과 merging을 도울 수 있어야 한다.


도구에 대한 이야기는 충분하니 개발 모델에 대해 이야기해보자. 앞으로 소개할 모델은 기본적으로 모든 팀원이 소프트웨어 개발 과정을 관리하기 위해 따라야 하는 절차에 지나지 않는다.


---

### Hotfix branches
> Hotfix branch : master branch로부터 나와 develop나 master 브랜치로 병합된다.

  Hotfix branches들은 비록 계획되지는 않았지만 새로운 배포를 준비한다는 점에서 release branch와 매우 흡사하다. Hotfix branch는 배포되어 있는 버전의 불만족스러운 상태를 즉각적으로 보완하기 위해 만들어졌다. 생산 버전에 있는 치명적인 bug를 즉시 해결해야 할 때, hotfix branch는 생산 버전을 표기하는 master branch와 일치하는 tag에서 떨어져 나온다. 중요한 건 hotfix의 보완 작업이 진행되는 동안 팀원들의 개발(develop branch)이 지속될 수 있다는 것이다.

### Summary
  이 branching 모델에서 충격적인 것은 없지만, 이 게시물의 시작에 있는 "big picture"그림은 우리의 프로젝트에서 매우 유용하다는 것을 알게 되었다. 이것은 이해하기 쉽고 팀원들이 branching과 releasing 과정을 공유할 수 있도록 만드는 우아한 정신이 깃든 모델이다.

---
