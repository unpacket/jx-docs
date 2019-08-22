---
title: Decisions
linktitle: Decisions
description: Documented decisions made by the Jenkins X project
date: 2018-06-29
publishdate: 2017-06-29
lastmod: 2018-06-29
menu:
  docs:
    parent: "about"
    weight: 40
weight: 40
sections_weight: 40
draft: false
aliases: [/about/decisions]
categories: [fundamentals]
toc: true
---

# Decisions

Jenkins X는 의견이 많은 개발자 경험입니다. 여기에서는 이러한 의견에 대한 이유를 설명하기 위해 취한 배경과 결정에 대해 설명합니다. Jenkins X가 권장하는 기능을 구현하는 방법에 대한 자세한 내용은 [Accelerate](https://jenkins-x.io/about/opinions/) 페이지를 참조하십시오.

## Kubernetes

첫 번째 이유는 Jenkins X가 Kubernetes에 전적으로 초점을 맞추고 실행하기위한 것입니다.

Kubernetes는 클라우드 전쟁에서 승리했으며 이제 모든 주요 클라우드 제공 업체는 Kubernetes를 지원하거나 Kubernetes 솔루션을 적극적으로 연구하고 있습니다. Google, Microsoft, Amazon, Red Hat, Oracle, IBM, Alibaba, Digital Ocean, Docker, Mesos 및 Cloud Foundry 등이 있습니다. 이제 일류 휴대용 응용 프로그램을 대상으로 개발할 수있는 배포 플랫폼이 하나 있습니다.

Kuberetes 생태계는 혁신이 풍부하고 활기차고 미래 지향적이며 다양한 오픈 소스 커뮤니티가있어 모든 관련자들에게 훌륭한 것을 제안합니다. Jenkins X는 가능하면 퍼블릭 클라우드 관리 형 Kubernetes 클러스터를 사용하는 것이 좋습니다. GKE, AKS 및 EKS는 모두 Kubernetes 마스터를 무료로 관리하고 운영합니다. 응용 프로그램을 실행하는 데 필요한 작업자 리소스 비용을 지불합니다 이는 Kubernetes 클러스터의 설치, 업그레이드 및 유지 관리 위험을 크게 줄입니다.

즉, 컨테이너를 실행하고 클러스터를 대규모로 관리하는 방법을 알고있는 사람들에게 비즈니스에 가치를 더하는 데 집중할 수 있도록하십시오.


## Draft

[Draft](https://draft.sh) 에는 몇 가지 기능이 있지만 Jenkins X는 언어 감지 및 팩 작성 기능 만 사용합니다. Jenkins X는 Jenkins X와 함께 실행되도록 맞춤식 [draft packs](https://github.com/jenkins-x-buildpacks/jenkins-x-kubernetes) 을 유지 관리합니다.

Draft는 Kubernetes에서 애플리케이션을 실행하는 데 필요한 패키징으로 소스 코드 프로젝트를 부트 스트랩하는 좋은 방법을 제공합니다.

Draft 프로젝트는 Microsoft가 인수 한 Deis에서 왔으며 Kubernetes 개발자 스토리에 지속적으로 투자하고 발전시키고 있습니다

## Helm

[Helm](https://helm.sh)은 Kubernetes에서 응용 프로그램을 실행하기위한 템플릿 패키지를 제공합니다. Helm 사용에 대한 의견이 혼합되어 있습니다.여러 Helm 차트를 함께 템플릿하고 구성 할 수있는 경험을 통해 매우 반가운 발견이었습니다. 이를 통해 Helm을 사용하여 전체 환경을 작성, 설치 및 업그레이드하고 값으로 쉽게 재정의 할 수 있습니다.예를 들어 환경 당 여러 복제본 또는 응용 프로그램 리소스 제한과 같은


OpenShift 템플릿은 비슷한 작업을 수행하는 것을 목표로하지만 OpenShift 전용입니다.

Helm 3의 주요 버전 업그레이드로 Helm에 대한 많은 우려가 해결되고 있습니다. Tiller 사용을 제거하면 Helm의 서버 측 구성 요소가 큰 승리입니다. 실행 권한이 높아지면 안전하지 않은 것으로 보입니다. Jenkins X는 https://jenkins-x.io/architecture/helm3/ 에서 Helm 3 베타 버전을 대신 사용하려는 사람들에게 대신 사용할 수있는 방법을 제공합니다. 우리는 이것을 직접 사용하고 있으며 지금까지 잘 작동하고 있습니다. 문제가있는 경우 Helm 프로젝트에 피드백을 보내 주시면 더 빨리 GA에 문의 할 수 있습니다.

Helm 프로젝트는 Microsoft가 인수 한 Deis에서 왔으며 Kubernetes 개발자 스토리에 계속 투자하고 발전시키고 있습니다. 

## Skaffold

Jenkins X는 [Skaffold](https://github.com/GoogleContainerTools/skaffold)를 사용하여 파이프 라인에서 빌드 및 푸시 이미지 작업을 수행합니다. 
Skaffold를 사용하면 [Google Container Buidler](https://cloud.google.com/container-builder/), [Azure Container Builder](https://github.com/Azure/acr-builder) 및 [ECR](https://aws.amazon.com/ecr/)과 같은 다양한 이미지 빌더 및 레지스트리 서비스를 구현할 수 있습니다.  

컨테이너 빌더 또는 레지스트리 서비스를 사용하여 퍼블릭 클라우드에서 실행되고 있지 않은 사람들을 위해 Skaffold는 [kaniko](https://github.com/GoogleContainerTools/kaniko) 와도 함께 작동 할 수 있으며,이를 통해 파이프 라인은 루트가없는 컨테이너를 사용하여 도커 이미지를 구축 할 수 있습니다. 이는 클러스터의 각 노드에서 도커 소켓을 마운트하는 것보다 훨씬 안전합니다.

## Jenkins

고 가용성이 아닌 대형 JVM 인 Jenkins는 클라우드에서 사용할 파이프 라인 엔진으로 선정 된 것은 놀라운 일입니다.그러나 개발자와 커뮤니티에서 Jenkins를 채택한 것은 현실적인 사용의 의미와  그들의 클라우드를 발전시키기 위한 이야기 입니다.  Jenkins X는 이미 Jenkins를 쿼리하는 대신 IDE 및 CLI 도구에서 사용하는 파이프 라인 활동에 대한 Kubernetes 사용자 정의 리소스 정의를 생성합니다. Jenkins 빌드를 저장하고 객체를 $ JENKINS_HOME이 아닌 Kubernetes에 저장하여 Jenkins 마스터를 확장 할 수 있습니다. 또한 Jenkins를 사용하지 않고 Git 웹 후크 이벤트를 가로 채기 위해 Prow로 전환하고 있습니다. 이는 고 가용성 솔루션을 보유하고 Kubernetes에 빌드 일정을 넘길 수 있음을 의미합니다.

TL; DR 우리는 더 많은 Jenkins 마스터 기능을 Kubernetes 플랫폼으로 푸시하고 있습니다.

이 접근 방식을 취하면 향후 다른 파이프 라인 엔진도 지원할 수 있습니다.

## Prow

[Prow](https://github.com/kubernetes/test-infra/tree/master/prow)는 Git 이벤트를 처리하고 Kubernetes에서 워크 플로를 트리거 할 수 있습니다.

Prow는 webhook 들어오는 URL에 대한 여러 파드가있는 고 가용성 모드에서 실행될 수 있습니다. Jenkins와 달리 업그레이드를 수행하는 경우 Jenkins에는 웹 후크 이벤트를 놓칠 수있는 가동 중지 시간이 있습니다. 이것은 향후 계획에 있으며 곧 제공 될 수 있기를 바랍니다.

## Nexus

[Nexus](https://help.sonatype.com/repomanager3)는 최근에 OSGi로 이동 한 과체중 JVM이지만 필요한 작업을 수행합니다. 빠른 빌드를 위해 종속성을 캐시하고 팀이 릴리스 된 아티팩트를 공유 할 수있는 공유 저장소를 제공하십시오.

누군가 Go와 같이보다 클라우드 친화적 인 언어로 오픈 소스 아티팩트 리포지토리 서버를 개발했다면 Jenkins X는 클라우드 요금을 절약하도록 전환 할 것입니다.

현재 Jenkins X는 Nexus의 도커 레지스트리를 사용하지 않습니다. 주된 이유는 인증 된 레지스트리를 사용할 수 있도록 이미지 풀 비밀을 사용하여 포드 정의를 설정하는 작업이 필요했기 때문입니다. 그러나 우리가 선호하는 방법은 Skaffold의 도움을 받아 Amazon의 [ECR](https://aws.amazon.com/ecr/), [Google Container Regitry](https://cloud.google.com/container-registry/) 또는 Dockerhub와 같은 기본 클라우드 공급자 레지스트리를 사용하도록 전환하는 것입니다.


## Docker registry

위와 같이 Amazon의 [ECR](https://aws.amazon.com/ecr/), [Google Container Regitry](https://cloud.google.com/container-registry/) 또는 Dockerhub와 같은 클라우드 공급자 레지스트리를 Skaffold의 도움으로 사용하는 것을 선호하므로 [레지스트리](https://github.com/kubernetes/charts/tree/master/stable/docker-registry)를 장기간 사용하지 않을 것입니다.

## ChartMuseum

Jenkins X를 만들 때 Helm Charts를 게시하는 방법에 대한 몇 가지 옵션이 있었지만 Kubernetes 커뮤니티는 GitHub 페이지를 사용하지만 모든 git 공급자를 사용하는 사람들에게 적합한 솔루션을 찾고 싶었습니다. [ChartMuseum](https://github.com/kubernetes-helm/chartmuseum)은 Go로 작성되었으므로 클라우드에서 잘 수행되며 여러 클라우드 스토리지를 지원하며 Monocular와 잘 작동합니다

## Monocular

우리는 [Monocular](https://github.com/kubernetes-helm/monocular)를 사용하여 Teams에서 게시 한 응용 프로그램을 검색합니다. 커뮤니티에서 선호하는 경우 기본적으로 KubeApps를 대신 사용할 수 있지만 KubeApps를 애드온으로 사용할 수 있습니다.


## Git

Jenkins X는 Git에서만 작동합니다. Jenkins X는 이미 다른 Git 공급자를 지원해야하는 많은 종속성 및 클라이언트 구현이 있습니다. 다른 버전 제어 시스템을 지원해야하는 수요가 충분하지 않으므로 현재 Jenkins X는 Git에 연결되어 있습니다.

## Programming languages

Jenkins X는 개발자가 애플리케이션의 성능을 이해하고 기능과 클라우드에서 더 잘 실행되는 다른 언어를 쉽게 실험 할 수있는 방법을 제공 할 수 있도록 올바른 피드백을 제공하는 것을 목표로합니다. 예를 들어 Java 응용 프로그램을 작성, 실행 및 유지 관리하는 방법 만 알고있는 많은 Java 기반 조직이 있습니다. Java는 Golang, Rust, Swift, NodeJS와 비교할 때 리소스를 많이 사용하므로 매월 클라우드 요금이 훨씬 높아집니다. Jenkins X를 사용하면 개발자가 Grafana 및 Prometheus와 같은 빠른 시작 및 메트릭 애드온을 사용하여 클라우드에서 어떻게 작동하는지 확인할 수있는 다른 옵션을 실험 할 수 있습니다.

예를 들어 Jenkins X 프로젝트에 구축 한 새로운 마이크로 서비스는 클라우드 사용료에 큰 영향을 미치므로 Golang 또는 NodeJS에있는 경향이 있습니다. 새로운 프로그래밍 언어로 전환하는 데 시간이 걸리지 만 Jenkins X에서는 빠른 시작, 자동화 된 CI / CD 및 모든 언어에서 비교적 일관된 작업 방식을 사용하여 많은 위험을 완화 할 수 있기를 바랍니다.

### Maven
Maven에는 CD에 적합하지 않은 많은 사람들이 사용하는 도구가 있습니다. 예를 들어, [maven release plugin](http://maven.apache.org/maven-release/maven-release-plugin/)인은 프로젝트 버전을 지정하고 CD 세계에서 다른 릴리스를 트리거하여 재귀 루프를 발생시키는 새로운 다음 SNAPSHOT 버전을 마스터하도록 직접 커밋합니다.

Java 프로젝트의 경우 Jenkins X는 [maven version:set plugin](https://www.mojohaus.org/versions-maven-plugin/set-mojo.html)인을 사용하여 위에서 언급 한 #Versioning 단계 다음에 다음 릴리스 버전을 사용하여 프로젝트의 모든 폼을 업데이트합니다.

새로운 메이저 또는 마이너 버전 증분이 필요한 경우 사용자는 새로운 메이저 / 마이너 번호로 새 Git 태그를 만들 수 있으며 Jenkins X는이를 존중합니다. 또는 부모 pom.xml과 자식 pom 파일을 직접 업데이트 할 수 있으며 Jenkins X는 새로운 주 버전 또는 부 버전을 감지하고 사용합니다.

