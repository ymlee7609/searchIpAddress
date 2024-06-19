first github file


(new) ==================
ipinfo sqlite db 파일을 만드는 과정

create table ipinfo
(
"망구분"	TEXT,
"할당단계"	TEXT,
"IP주소 체계"	TEXT,
"IP주소"	TEXT,
"서브넷"	INT,
"IP주소 범위"	TEXT,
"IPAddr_From"	 TEXT,
"IPAddr_To"	TEXT,
"IPAddr_Int_From"	INT,
"IPAddr_Int_To"	INT,
"관리팀"	TEXT,
"장비명"	TEXT,
"연동장비명"	TEXT,
"용도"	TEXT,
"비고"	TEXT,
"IDC고객명"	TEXT,
"IDC고객ID"	TEXT,
"상태"	TEXT,
"중복체크자"	TEXT,
"할당요청부서" TEXT
);

.separator ,
.import IP_info_sample_02.csv ipinfo

create index ipinfo_idx on ipinfo ("IPAddr_Int_From", "IPAddr_Int_To");

.save ipinfo_sample_02_01.db


(old) ==================
ipinfo sqlite db 파일을 만드는 과정

create table ipinfo
(
"망구분"	TEXT,
"할당단계"	TEXT,
"IP주소 체계"	TEXT,
"IP주소"	TEXT,
"서브넷"	INT,
"IP주소 범위"	TEXT,
"IP주소 시작"	 TEXT,
"IP주소 종료"	TEXT,
"IP주소 숫자 시작"	INT,
"IP주소 숫자 종료"	INT,
"관리팀"	TEXT,
"장비명"	TEXT,
"연동장비명"	TEXT,
"용도"	TEXT,
"비고"	TEXT,
"IDC고객명"	TEXT,
"IDC고객ID"	TEXT,
"상태"	TEXT,
"중복체크자"	TEXT,
"할당요청부서" TEXT
);

.impoprt IP_info_sample.csv ipinfo

create index ipinfo_idx on ipinfo ("IP주소 숫자 시작", "IP주소 숫자 종료");

.save ipinfo.db
