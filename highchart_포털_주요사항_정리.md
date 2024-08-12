## 주요 활용 코드 정리


### 스택 레이블 : Y-axis에 들어감

```javascript
"stackLabels": {
    "enabled": true,
    "verticalAlign": "top",
    "y": -5,
    "style": {
        "fontSize": 13,
        "fontWeight": "normal"
    }
}
```

### 가운데 선넣기 : Y-axis에 들어감
```javascript
"plotLines": [{
    "color": "#fe6a35",
    "width": 2,
    "value": 12.8,
    "zIndex": 5,
    "dashStyle": "dash",
    "label": {
        "text": "평년평균(12.8도)",
        "align": "left",
        "y": -15,
        "x": -2,
        "style": {
            "textOutline": "white",
            "strokeWidth": 2,
            "fontWeight": "bold"
        }
    }
}]
```

### 값 최대,최소, 인터벌 설정 : Y-axis

```javascript
"yAxis": {
    "title": {
        "text": "백만톤 Co2eq"
    },
    "max": 800,
    "tickInterval": 200
}
```


### 차트에 패턴넣기 : 각 데이터 뒤에 옵션에 넣음
```javascript
"color": {
    "patternIndex": 8
},
"borderWidth": 1,
"dashStyle": "dash",
"borderColor": "orange"
```



	    
## 예시1 : 질소산화물 배출량(Nox) 자료 그래프 (누적 Bar차트)

### 전체 코드 참고
```javascript
Highcharts.setOptions({
    lang: {
        numericSymbols: null,
        thousandsSep: ','
    }
});

Highcharts.chart(previewBox, {
  "title": {
    "text": "질소산화물(Nox) 배출량"
  },
  "series": [
    {
      "name": "에너지산업 연소",
      "data": [
        150818,
        145445,
        114192,
        104420,
        75513,
        53295,
        "",
        ""
      ]
    },
    {
      "name": "비산업 연소",
      "data": [
        82948,
        85824,
        86803,
        87599,
        85814,
        82593,
        "",
        ""
      ]
    },
    {
      "name": "제조업 연소",
      "data": [
        169139,
        175332,
        169790,
        168967,
        169221,
        125417,
        "",
        ""
      ]
    },
    {
      "name": "생산공정",
      "data": [
        59830,
        55932,
        53618,
        57020,
        51705,
        43865,
        "",
        ""
      ]
    },
    {
      "name": "도로이동오염원",
      "data": [
        369585,
        452995,
        434038,
        406227,
        371851,
        309387,
        "",
        ""
      ]
    },
    {
      "name": "비도로이동오염원",
      "data": [
        304376,
        309986,
        309309,
        307942,
        311748,
        295606,
        "",
        ""
      ]
    },
    {
      "name": "폐기물처리",
      "data": [
        11977,
        13570,
        12994,
        12492,
        12332,
        10497,
        "",
        ""
      ]
    },
    {
      "name": "기타 면오염원",
      "data": [
        172,
        167,
        214,
        184,
        271,
        252,
        "",
        ""
      ]
    },
    {
      "name": "생물성 연소",
      "data": [
        8883,
        9059,
        8841,
        8413,
        8407,
        8316,
        "",
        ""
      ]
    },
    {
      "name": "목표치",
      "data": [
        "",
        "",
        "",
        "",
        "",
        "",
        658163,
        539438
      ],
     "color": {        
         patternIndex: 8,
       },
       borderWidth:1,
       dashStyle:'dash',
       borderColor:'orange'
    }
  ],


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
	}
    },
  },

  # Bar차트 선택
  "chart": {
    "type": "column"
  },

  "xAxis": {
    "categories": [
      "2015",
      "2016",
      "2017",
      "2018",
      "2019",
      "2020",
      "2027(목표)",
      "2032(목표)"
    ]
  },
  "legend": {
    "layout": "horizontal",
    "align": "center",
    "verticalAlign": "bottom"
  },

  # 차트 속성
  "plotOptions": {
    "column": {
      "stacking": "normal",
      "dataLabels": {
        "enabled": false
      }
    }
  }
});
```

### 주요수정사항
1) 누적 Bar차트 선택
2) 데이터 레이블 제거
   
```javascript
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
```javascript
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
    ...
  }
```

4) 목표치 차트모양 변경 (해당 y축 부분에 추가)

```javascript
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
...
```

## 예시2 : 기온 자료 그래프 (Bar차트)


### 전체 코드
```javascript
Highcharts.chart(previewBox, {
  "title": {
    "text": "연평균기온"
  },
  "series": [
    {
      "name": "평균기온",
      "data": [
        12.4,
        12.1,
        12.1,
        12.6,
        12.8,
        13.1,
        13.4,
        12.8,
        12.8,
        13.3,
        13,
        13.3,
        12.9,
        "",
        "",
        ""
      ]
    },
    {
      "name": "전망치",
      "data": [
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        "",
        13,
        13.5,
        14
      ],
     color: {	
         patternIndex: 8,
       },
       borderWidth:1,
       dashStyle:'dash',
       borderColor:'orange'
    }
  ],
  "yAxis": {
    "title": {
      "text": "°C"
    },
      "min" : 10,
       plotLines: [{
        color: '#fe6a35',
        width: 2,
        value: 12.8,
        zIndex: 5,
        dashStyle : 'dash',
        label: {
            text: '평년평균(12.8°C)',
            align: 'left',
            y: -15,     
            style: {		
	          textOutline: 'white',
	          strokeWidth: 2,
	          fontWeight : 'bold'
            }
        }}]
  },
  "chart": {
    "type": "column"
  },
  "xAxis": {
    "categories": [
      "2010",
      "2011",
      "2012",
      "2013",
      "2014",
      "2015",
      "2016",
      "2017",
      "2018",
      "2019",
      "2020",
      "2021",
      "2022",
      "2030(전망)",
      "2040(전망)",
      "2050(전망)"
    ]
  },
  "legend": {
    "layout": "horizontal",
    "align": "center",
    "verticalAlign": "bottom"
  },
  "plotOptions": {
    "column": {
      "stacking": "normal",
      "dataLabels": {
        "enabled": true
      }
    }
  }
});
```

### 주요수정사항
```javascript
 "yAxis": {
    "title": {
      "text": "기온(°C)"
    },

    # 최소값 지정
    "min" :10,

    # Plotline 만들기
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
```

