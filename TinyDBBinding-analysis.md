# TinyDBBinding

TinyDB 테이블 구조 및 리소스 

<img width="721" alt="image" src="https://github.com/leesangwooon/ACME/assets/144790879/a1dd72aa-db28-4f5e-b220-d59e7b25aad7">

(기본적으로 메서드에서의 작업은 with self.lock~ 블럭 내에서 이루어짐 -> 작업에 앞서 테이블 단위로 락을 걸어 동기화 문제 해결)

#### _assignConfig()
cacheSize, writeDelay,maxRequests 받아옴 (Configuration.py)

#### closeDB()
db의 모든 테이블 연결 해제 (TinyDB Table.close() 이용)

#### purgeDB()
db의 모든 테이블 삭제 (TinyDB Table.truncate() 이용)

#### backupDB
db의 모든 테이블의 데이터(메타데이터 포함)을 복사하여 인자로 받은 dir 경로에 저장 (pathlib 모듈 Path(), shutil 모듈 copy2() 이용)

## Resources - resources table

#### insertResource()
테이블에 리소스 insert (TinyDB Table.insert() 이용)

#### upsertResource()
테이블에 리소스 update or insert (TinyDB Table.upsert() 이용)

#### updateResource()
테이블에 리소스 update 및 해당 리소스 딕셔너리 내 null 데이터 삭제 (TinyDB Table.update() 이용)

#### deleteResource()
테이블에 리소스 delete (TinyDB Table.remove() 이용)

#### searchResources()
인자로 받은 데이터 기반으로 해당 데이터를 포함하는 리소스 리스트 반환 (TinyDB Table.search() 이용)

#### discoverResourcesByFilter()
필터 함수(입력: JSON, 출력:bool) 조건에 맞는 리소스 리스트 반환 (TinyDB Table.search() 이용)

#### hasResource()
인자로 전달받은 데이터를 포함하는 리소스 존재 여부 반환 (TinyDB Table.contains() 이용)

#### countResources()
리소스의 개수 반환 (파이썬 내장함수 len() 이용)

#### searchByFragment()
인자로 전달받은 딕셔너리의 리소스를 검색하여 리스트로 반환 (TinyDB Table.search() 이용)

## Identifiers - identifiers/srn/children table

#### upsertIdentifier()
identifiers 테이블에 (ri, rn, srn, ty), srn 테이블에 (srn, ri) update or insert (TinyDB Table.update() 이용)

#### deleteIdentifier()
identifiers 테이블, srn 테이블에서 인자로 받은 리소스에 대한 ri, srn 각각 삭제  (TinyDB Table.remove() 이용)

#### searchIdentifiers()
identifiers 테이블, srn 테이블에서 ri, srn 기반 리소스 검색하여 리스트로 반환 (TinyDB Table.get() 이용)

#### upsertChildResource()
children 테이블에 리소스 upsert 후 부모 리소스와 자식 리소스 연결 (TinyDB Table.upsert/get/update() 이용)

#### removeChildResource()


#### searchChildResourcesByParentRI()


## Subscriptions 		

#### searchSubscriptions()
#### upsertSubscription()
#### removeSubscription()


## BatchNotifications 

#### addBatchNotification()
#### countBatchNotifications()
#### getBatchNotifications()
#### removeBatchNotifications()

## Statistics 		

#### searchStatistics()
#### upsertStatistics()
#### purgeStatistics()

## Actions	 			

#### searchActionReprs()
#### getAction()
#### searchActionsDeprsForSubject()
#### upsertActionRepr()
#### updateActionRepr(()
#### removeActionRepr()

## Requests	 		

#### insertRequest()
#### getRequests()
#### deleteRequests()
 

## Schedules	 		

#### getSchedules()
#### getSchedule()
#### searchSchedules()
#### upsertSchedule()
#### removeSchedule()
