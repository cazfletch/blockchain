---

copyright:
  years: 2017
lastupdated: "2017-12-05"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 네트워크 통제
{: #getting-started-with-blockchain}

{{site.data.keyword.Bluemix_notm}}에서 {{site.data.keyword.blockchainfull}} Platform은 높은 보안, 무결성, 확장성 및 성능의 {{site.data.keyword.blockchain}} 네트워크를 제공합니다. 완전히 기능적인 {{site.data.keyword.blockchain}} 네트워크를 빠르게 프로비저닝하고 네트워크 모니터를 사용하여 사설 블록체인 네트워크를 설계하고 구성할 필요 없이 체인코드 및 애플리케이션을 즉시 실행할 수 있습니다.
{:shortdesc}
 
이 시작하기 튜토리얼에서는 {{site.data.keyword.blockchain}} 네트워크를 IBM의 가용성이 높고 안전한 환경에 호스팅하기 위해 따라야 하는 단계 및 전제조건을 소개합니다.   

다음 단계는 다중 멤버 조직이 있는 {{site.data.keyword.blockchain}} 네트워크를 시작하기 위한 기본 플로우를 나타냅니다. 
1. **네트워크 개시자**는 네트워크 멤버의 한 가지 특수한 유형으로서 {{site.data.keyword.blockchain}} 네트워크를 작성하고 통제 정책을 정의합니다. 그러면 네트워크 개시자는 이 {{site.data.keyword.blockchain}} 네트워크에 네트워크 멤버로 가입하도록 다른 기관을 초대할 수 있습니다. 세부사항은 [네트워크 작성](#creating-a-network)을 참조하십시오.
2. **네트워크 멤버**는 {{site.data.keyword.blockchain}} 네트워크에 가입하기 위한 지시사항을 제공하는 이메일 알림을 수신합니다. 이메일 알림의 지시사항 외에도 [네트워크 가입](#joining-a-network)의 단계를 따를 수도 있습니다. 
3. 모든 **네트워크 멤버**는 네트워크를 작성하거나 가입한 후에 자신의 네트워크 리소스를 구성하고 관리하기 위해 GUI 대시보드인 네트워크 모니터를 입력할 수 있습니다. 네트워크 멤버의 그룹으로 채널을 설정하여 채널 멤버만 액세스할 수 있는 채널 특정 원장에서 개인용 트랜잭션을 실행할 수 있습니다. 네트워크 모니터에서 사용자 자신의 피어를 채널에 가입하고 거기에 체인코드를 설치하고 인스턴스화할 수도 있습니다. 세부사항은 [네트워크 리소스 및 환경 구성](#configuring-network-resources-and-environment)을 참조하십시오.
4. **애플리케이션 개발자**는 {{site.data.keyword.blockchain}} 네트워크와 상호작용을 사용 가능하게 하는 애플리케이션을 작성합니다. 자세한 정보는 [애플리케이션이 네트워크와 상호작용할 수 있도록 설정](#enabling-applications-to-interact-with-the-network)을 참조하십시오.
5. **네트워크 운영자**는 네트워크 모니터를 사용하여 자신의 채널에서 트랜잭션을 모니터합니다. 세부사항은 [네트워크 리소스 모니터링](#monitoring-network-resources)을 참조하십시오.

## 네트워크 작성
시작하기 전에 {{site.data.keyword.Bluemix_notm}}에서 [{{site.data.keyword.blockchain}} Platform 서비스 인스턴스 ![외부 링크 아이콘](images/external_link.svg "외부 링크 아이콘")](https://console.bluemix.net/catalog/services/blockchain)을 작성해야 합니다. {{site.data.keyword.Bluemix_notm}} ID로 로그인해야 합니다. ID가 없는 경우, **계정 작성을 위해 등록** 단추를 클릭하십시오. 나중에 쉽게 알아볼 수 있도록 사용자의 인스턴스에 대한 서비스 및 신임 정보 이름을 바꾸십시오. {{site.data.keyword.blockchain}} 네트워크를 배치할 수 있는 {{site.data.keyword.Bluemix_notm}} 지역, 조직 및 영역을 선택하십시오. 그리고 가격 책정 플랜 표에서 **엔터프라이즈 플랜**을 선택하고 **작성** 단추를 클릭하십시오.  

{{site.data.keyword.blockchain}} Platform 서비스 인스턴스를 [{{site.data.keyword.Bluemix_notm}} 서비스 대시보드 ![외부 링크 아이콘](images/external_link.svg "외부 링크 아이콘")](https://console.bluemix.net/dashboard/services "{{site.data.keyword.Bluemix_notm}} 서비스 대시보드")에서 찾을 수 있습니다.  

네트워크 개시자인 경우, **네트워크 작성** 단추를 클릭하여 {{site.data.keyword.blockchain}} 네트워크를 시작하십시오. 마법사를 따라서 사용자의 네트워크 및 리소스의 기본 구성을 완료하십시오.  
![네트워크 작성 마법사](images/create_network_name.png "네트워크 작성 마법사")  

1. "시작하기" 화면에서 네트워크에 이름을 지정하고 {{site.data.keyword.Bluemix_notm}} 조직의 위치를 선택하고 기관의 이름을 추가하십시오. 사용자가 다른 네트워크 멤버를 초대하면 그 멤버들이 가입하기 위해 이 네트워크 이름을 찾게 됩니다. **다음**을 클릭하십시오. 
2. (선택사항) "멤버 초대" 화면에서 사용자의 네트워크에 초대하려는 멤버의 이메일 주소 및 기관 이름을 입력하십시오. 사용자가 지정하는 기관 이름은 공식 호칭이 아닙니다. 단순히 기관을 쉽게 인식할 수 있도록 하기 위한 것이며 네트워크에 가입할 때 변경할 수 있습니다. 참고로 네트워크에는 사용자 자신을 포함하여 최대 15개의 멤버가 가능합니다. 이 단계는 선택사항이며 나중에 네트워크 모니터에서 멤버를 네트워크에 초대할 수 있습니다.  **다음**을 클릭하십시오.
	 사용자가 초대하는 멤버는 네트워크 작성을 위한 모든 단계를 완료한 후에 초대에 대한 이메일 알림을 수신하게 됩니다. 
3. "통제 규칙 정의" 화면에서 멤버십, 채널 작성 및 체인코드에 대한 정책을 설정하십시오. 기본적으로 모든 네트워크 멤버는 다른 멤버를 네트워크에 가입하도록 초대해서 채널을 작성하고 체인코드를 인스턴스화할 수 있습니다. 이 GA의 경우, 네트워크는 기본 통제 정책을 사용합니다. **다음**을 클릭하십시오. 
4. "검토 요약" 화면에서 네트워크 구성을 확인하십시오. 수정사항을 작성하려는 경우, 섹션 헤더 옆의 **편집**을 클릭하거나 **이전** 단추를 클릭하여 이전 화면으로 돌아가십시오. 네트워크 구성을 완료하면 **완료**를 클릭하십시오.   
5. "작성된 네트워크" 화면에서 사용자의 네트워크가 작성되었다는 알림을 받게 됩니다. **피어 추가**를 클릭하여 네트워크 리소스를 구성하거나 **모니터 입력**을 클릭하여 직접 네트워크 모니터를 열 수 있습니다. 먼저 피어를 추가하지 않는 경우, 네트워크 모니터에서 나중에 추가할 수 있습니다. 피어에 대한 자세한 정보는 [개요](v10_dashboard.html#overview)를 참조하십시오.
    
이제 다음 네트워크 리소스를 지원할 수 있는 {{site.data.keyword.blockchain}} 네트워크를 배치할 준비가 되었습니다.   
* 멤버 특정 인증 기관(CA)
* 기본 통제 정책
* 최대 15개의 네트워크 멤버  
* 세 개의 순서 지정자 및 두 개의 중간 CA 노드
* 각 멤버에 최대 세 개의 작은 피어  
* 충돌 결함 허용 순서 지정 서비스
* 최대 150개의 채널
* 최대 10개의 체인코드 인스턴스화


## 네트워크 가입
네트워크 작성과 비슷하게 {{site.data.keyword.Bluemix_notm}}에서 [{{site.data.keyword.blockchain}} Platform 서비스 인스턴스 ![외부 링크 아이콘](images/external_link.svg "외부 링크 아이콘")](https://console.bluemix.net/catalog/services/blockchain)을 작성해야 합니다. {{site.data.keyword.Bluemix_notm}} ID로 로그인해야 합니다. ID가 없는 경우, **계정 작성을 위해 등록** 단추를 클릭하십시오. 나중에 쉽게 알아볼 수 있도록 사용자의 인스턴스에 대한 서비스 및 신임 정보 이름을 바꾸십시오. {{site.data.keyword.blockchain}} 네트워크를 배치할 수 있는 {{site.data.keyword.Bluemix_notm}} 지역, 조직 및 영역을 선택하십시오. 그리고 가격 책정 플랜 표에서 **엔터프라이즈 플랜**을 선택하고 **작성** 단추를 클릭하십시오.  

{{site.data.keyword.blockchain}} Platform 서비스 인스턴스를 [{{site.data.keyword.Bluemix_notm}} 서비스 대시보드 ![외부 링크 아이콘](images/external_link.svg "외부 링크 아이콘")](https://console.bluemix.net/dashboard/services "{{site.data.keyword.Bluemix_notm}} 서비스 대시보드")에서 찾을 수 있습니다. 

사용자가 초대된 네트워크 멤버인 경우, **보류 중인 초대 ->** 단추를 클릭하고, 드롭 다운 목록에서 가입하려는 네트워크를 선택하고, **네트워크 가입!** 단추를 클릭하십시오. 마법사를 따라서 사요자 네트워크의 네트워크 기본 구성을 보고 사용자 자신의 네트워크 컴포넌트를 구성하십시오.  
![네트워크 가입 마법사](images/join_network_name.png "네트워크 가입 마법사")  

1. "시작하기" 화면에서 기관의 이름을 추가하고 {{site.data.keyword.Bluemix_notm}} 조직의 위치를 확인하십시오. **다음**을 클릭하십시오. 
2. "통제 규칙 검토" 화면에서 멤버십, 채널 작성 및 체인코드의 네트워크 통제 정책을 보십시오. **다음**을 클릭하십시오. 
3. (선택사항) "피어 추가" 화면에서 추가하려는 피어의 크기 및 수량을 선택하십시오. **다음**을 클릭하십시오. 네트워크의 각 멤버는 최대 세 개의 피어를 추가할 수 있으며, 이 시점에는 "작은" 피어만 사용 가능합니다. 이 단계는 선택사항이며 나중에 네트워크 모니터에서 피어를 추가할 수 있습니다.  피어에 대한 자세한 정보는 [개요](v10_dashboard.html#overview)를 참조하십시오.
4. "네트워크 요약 검토" 화면에서 네트워크 구성을 확인하십시오. 수정사항을 작성하려는 경우, 섹션 헤더 옆의 **편집**을 클릭하거나 **이전** 단추를 클릭하여 이전 화면으로 돌아가십시오. 리소스 구성을 완료하면 **완료**를 클릭하십시오. 네트워크에 가입했다는 알림을 받게 됩니다. 그 다음에 **모니터 입력**을 클릭하여 네트워크 모니터를 열거나 **채널 작성**을 클릭하여 채널 작성 요청을 시작할 수 있습니다. 네트워크 모니터에서 나중에 채널을 작성할 수 있습니다. 자세한 정보는 [채널](v10_dashboard.html#channels)을 참조하십시오.
 

## 네트워크 리소스 및 환경 구성

1. {{site.data.keyword.blockchain}} 네트워크 작성 또는 가입 후에 네트워크 모니터를 입력하십시오. 네트워크 모니터는 네트워크 상태 정보의 추적을 관리하고 유지할 수 있는 GUI 대시보드입니다. 자세한 정보는 [네트워크 모니터](v10_dashboard.html)를 참조하십시오.
2. 네트워크에 사용자 자신의 피어를 추가하십시오. 피어를 이미 충분히 추가했으면 이 단계를 건너뛰십시오. 피어는 체인코드를 실행하며 사용자의 애플리케이션과 상호작용하기 위한 엔드포인트입니다. "개요" 화면에서 **피어 추가**를 클릭하고 피어의 수량 및 크기를 선택하십시오. 자세한 정보는 [개요](v10_dashboard.html#resources)를 참조하십시오.
3. 채널을 설정하십시오. 같은 채널의 모든 멤버에게 데이터 격리 및 기밀성을 전달하는 채널 특정 원장이 프로비저닝됩니다. 채널 작성 방법에 대한 정보는 [채널 작성](howto/create_channel.html#creating-a-channel)을 참조하십시오.  
	
	채널에 가입하도록 초대받은 채널 멤버인 경우, 사용자가 채널에 가입할 수 있도록 하는 마법사에 대한 링크가 있는 이메일 알림을 수신하게 됩니다.
4. 피어를 채널에 가입하십시오. 채널과 연관된 피어만 해당 원장에 액세스할 수 있습니다. 자세한 정보는 [채널](v10_dashboard.html#channels)을 참조하십시오.
5. 체인 코드를 설치하고 인스턴스화하십시오. 모든 채널 멤버는 체인코드를 실행할 모든 피어에 이름과 버전이 같은 동일한 체인코드를 설치해야 합니다. 설치 후에는 우선 체인코드를 채널에서 인스턴스화해야 사용할 수 있습니다. 자세한 정보는 [체인코드 설치 및 인스턴스화](howto/install_instantiate_chaincode.html)를 참조하십시오.  

**참고**: 고가용성을 얻기 위해 각 기관은 최소 두 개의 피어를 구매해야 하며, 각 참여 기관은 최소 두 개의 피어에서 가입해야 합니다. 

## 애플리케이션이 네트워크와 상호작용할 수 있도록 설정
애플리케이션은 SDK API를 활용하여 {{site.data.keyword.blockchain}} 네트워크 컴포넌트와 상호작용합니다. 애플리케이션이 트랜잭션 요청으로 피어를 결국 대상으로 지정할 수 있도록 사용자의 애플리케이션에서 네트워크 컴포넌트의 API 엔드포인트 정보를 추가해야 합니다. 그런 다음 네트워크 모니터에서 API 엔드포인트 정보를 추가할 수 있습니다. 애플리케이션은 로컬 파일 시스템 또는 {{site.data.keyword.Bluemix_notm}}에 호스팅될 수 있습니다. 자세한 정보는 [애플리케이션 개발](v10_application.html)을 참조하십시오.

## 네트워크 리소스 모니터링  
트랜잭션이 사용자의 애플리케이션에서 트리거된 후에 네트워크 모니터에서 트랜잭션 상태 정보를 볼 수 있습니다. 네트워크 모니터링에 대한 자세한 정보는 [네트워크 모니터링](howto/monitor_network.html)을 참조하십시오.
  
## 네트워크 나가기 
네트워크에서 나가려면 {{site.data.keyword.Bluemix_notm}} 대시보드에서 블록체인 서비스 인스턴스를 삭제하십시오.  

**참고**: 네트워크를 나가기 전에 네트워크 내의 채널의 멤버가 아닌지 확인하십시오. 멤버이면 네트워크를 나갈 때 오류가 발생합니다. 채널 업데이트 프로세스를 완료하려면 채널 멤버를 제거해야 합니다. 채널 업데이트 프로세스에 대한 자세한 정보는 [채널 업데이트](howto/create_channel.html#updating-a-channel)를 참조하십시오.


<!--
## References
* For more information about {{site.data.keyword.blockchainfull_notm}} offerings, see [Blockchain offerings](index.html).
* For more information about Hyperledger Fabric V1.0, see [Hyperledger Fabric documentation ![External link icon](images/external_link.svg "External link icon")](http://hyperledger-fabric.readthedocs.io/en/latest/){:new_window}.
-->