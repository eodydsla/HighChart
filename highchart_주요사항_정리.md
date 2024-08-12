## 대기배출량 자료 그래프 수정

1) 누적 Bar차트 선택
2) 데이터 레이블 제거
   
```
 "plotOptions": {
    "column": {
      "stacking": "normal",
      "dataLabels": {
        "enabled": false
      }
    }
...
}
```

3)  합계 레이블 표시
```
  "yAxis": {
    "title": {
      "text": "톤(ton)"
    },

    "stackLabels": {
                "enabled": true,
                "verticalAlign": "top",
                "y":-5,
                style: {
                fontSize: 13,
                fontWeight : 'normal'
                 },
            }
```

5) 목표치 차트모양 변경 (해당 y축 부분에 추가)

 "name": "목표치",
      "data": [
        "",
        "",
        "",
        "",
        "",
        "",
        902066,
        892028
      ],
      color: {        
          patternIndex: 8,
       },
       borderWidth:1,
       dashStyle:'dash',
       borderColor:'orange'



 "yAxis": {
    "title": {
      "text": "기온(°C)"
    },
    "min" :10,

    plotLines: [{
        color: '#fe6a35',
        width: 2,
        value: 12.8,
        zIndex: 5,
        dashStyle : 'dash',
        label: {
            text: '평년평균(12.8도)',
            align: 'left',
            y: -15,
            x: -2,
            style: {		
	          textOutline: 'white',
	          strokeWidth: 2,
	          fontWeight : 'bold'
            }
        }}]
  },

