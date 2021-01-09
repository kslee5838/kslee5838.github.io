2021년 1월 9일 일요일 오후 6시작성  

## xpath를 이용하여 XML 읽는 방법   


1. URL을 정한후 **`htmlTreeParse`** 를 이용하여 parse 한다  
2. **`htmlParse`** 와 다른 점은 무었일 까  
3. **`xmlToList`** 를 이용하여 정리 한다 
4. 예제 (공공데이터 등산정보) 

	> url4<-"http://openapi.forest.go.kr/openapi/service/cultureInfoService/gdTrailInfoOpenAPI?serviceKey=rnqqUlk9yLx%2FVIeSv%2FHRdO0Th0ulISq9imO26OYkiUXJINCpsMdzSJol0CI7urgGziwwH8%2Fd9iLRkrn5JOP8qA%3D%3D&searchArNm=%EA%B2%BD%EC%83%81%EB%82%A8%EB%8F%84&numOfRows=10&pageNo=2"
        
	> html04<-htmlTreeParse(url4)
  
	> html04<-htmlTreeParse(url4,useInternalNodes = T)
 
	> xmltop = xmlRoot(html04)

	> xpathSApply(html04,"///mntnm",xmlValue), 참고 class는 캐릭터   
  
	> xpathSApply(html04,"///@mntnm",xmlValue), 참고 class 는 리스트  
  
	> xmlToList(url4)%>%t()%>%data.frame()%>%unlist()

	-    ldply(xmlToList(url04),data.fram) 은 가로 줄이어서 이를 일기 좋게 세로로 편집하여 했는데 잘 안돼서 아래처럼
   파이프를 이용하여 처리 했음. 다음 코드 **xmlToList(url4)%>%t()%>%data.frame()%>%unlist()** 

