# TIL
04.18 (금)
오늘 SQL 4강을 복습차 들었다. 
오전에 풀었던 sql code kata에서 join 기능을 활용하는 법을 다시 점검하게 되었다.
오답노트를 작성중에 카테고리 별 도서의 판매량을 합산하는 문제 였는데, where절로 판매 주간을 지정하는걸 
누락했다는걸 알게되었다.
SELECT b.CATEGORY, SUM(bs.SALES) AS TOTAL_SALES
FROM BOOK b
JOIN BOOK_SALES bs
ON b.BOOK_ID = bs.BOOK_ID
WHERE bs.SALES_DATE LIKE '2022-01%'
GROUP BY b.CATEGORY
ORDER BY b.CATEGORY
