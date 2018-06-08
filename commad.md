# 명령어들





## 1.dir

directory : 폴더 안에 내용을 보여준다.



## 2. mkdir

make directory : 폴더를 만든다

ex) `mkdir project`



## 3. cd

- change directory : 폴더를 이동한다.
- 사용법 1 :` cd`(가고자 하는 폴더)
- 사용법 2 : `cd ..` (상위폴더)

tip) cd pro누른 뒤에 tab `cd project` (tab누를 시에 자동완성 기능)

- c\:루트 디렉토리(더이상 못올라감)

  

## github설치

- cmd 관리자 모드 실행 후 choco install git실행 Y입력
- 

## github

- github실행 후 cd project/로
- 글자 확대 ctrl+, 축소 ctrl-
- 

## Visual Studio code

- 경로 설정하여 저장 project에 .rb확장자로 저장
- 이후에 git hub에서 dir칠 시에 저장 파일보임
- 저장 파일을 실행 할 시에 vscode실행문에 따라 출력됨
- 

## 반복문 실행

- 실행하고자 하는 숫자.times는 해당숫자만큼 반복문 실행

  ex) 5.times do

  ​        puts "hello"

   end

​		5.times do

​    		print "hello"

​	end

 		5.times do

 		p "hello"

​	end

​	puts "조건문 입니다." if true



## 배열 each반복문

\# 배열

num = [25, 3, -100, 32, -45, 78]

str = ["안녕", " 잘가", "반가워"]

 

\# n = 0

\# while n < 6

\#     puts num[n]

\#     n += 1

\# end

 

\# ctrl+/는 해당 영역 주석

 

\# num.each do |x|

\#     puts x.even?

\# end

 

str.each do |babo|

​    puts babo + "아이유"

end



## lunch 무작위 추출

\# 1. 원하는 메뉴들을 저장한다.

\# 2. 그 메뉴들 중에 하나를 랜덤으로 뽑는다.

\# 3. 뽑는 메뉴를 출력한다.

 

menu = ["20층", "김밥", "순남", "양자강"]

 

puts [20, 100, -30, 0, 15, -45].sort.reverse.sample



## Lanunchy 브라우저

\# launchy 친구를 불러온다.

\# launchy에게 브라우저 열어달라고 한다.

 

require "launchy"

require "uri"  #url ==uri같은 말

 

\# "https://search.naver.com/search.naver?where=nexearch&sm=top_sug.pre&fbm=1&acr=2&acq=dkdldb&qdt=0&ie=utf8&query=multicampus"

\# Launchy.open()

 

keywords = ["방탄소년단", "워너원", "빅뱅"]

 

url = "https://search.naver.com/search.naver?where=nexearch&sm=top_sug.pre&fbm=1&acr=2&acq=dkdldb&qdt=0&ie=utf8&query="

keyword = keywords[0]

 

\# n = 0

\# while (n < 3)

\#     #반복시킬 문장을 넣으면 된다.

\#     Launchy.open(url + keywords[n])

\#     n = n + 1

\# end

 

keywords.each do |key|

​    Launchy.open(url + key)

end

 

puts key



## scrap

require 'httparty'

require 'nokogiri'

  

\# 1. naver에 원하는 정보가 담긴 페이지를 요청한다.

\# 2. 네이버에게 받은 문서 안에 있는 원하는 정보를 빼온다.

\# 3. 빼온 정보를 출력한다.

res = HTTParty.get("http://finance.naver.com/sise/")

val = Nokogiri::HTML(res).css("#speCurrencyColl > div.coll_cont > div > div.wrap_quote > div.graph_quote > div.graph_rate.stock_up > em.currency_value") #css:웹 꾸미는데 필요한 것

puts "현재 비트코인 가격은 " + val.text

## nogada

\# 1. 파일을 만든다 100개만

\#  - 특정 폴더로 들어간다.

\#  - 파일을 만든다.

\# 2. 파일들(100개)의 이름을 수정한다.

\# tip) mkdir로 만드는 것이 루비 코드로 사용가능.

 

Dir.pwd

\#pwd 내가 현재 폴더 위치 나옴

 

Dir.chdir("files")

20.times do |x|

\# puts Dir.entries(Dir.pwd)

\# #dir과 같은게 entries

 

​    File.open("list#{x}.txt", "w") do |f|

​        f.write("이건 테스트 파일입니다.")

​    end

end

 

\# name = "john"

\# puts "hello #{name} nice to meet you"