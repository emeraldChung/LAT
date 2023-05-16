# HW4 #


## Task-1 ##

單純的英文回復(positive, negative, netrual)

![Task1](https://github.com/emeraldChung/LAT/blob/main/Homework4/task1.jpg)



### Task-1程式碼 ###

按照老師課堂進度跟著做，沒有特別需要修正的部分



## Task-2 ##

將原本單純的英文回復(positive, negative, netrual)進一步切換成中文，並新增分數指標

![Task2](https://github.com/emeraldChung/LAT/blob/main/Homework4/task2.jpg)



### Task-2程式碼 ###

重新定義名稱，增加各層面的分數指標並合併

    const sentimentT = results[0].sentiment;
    const score = results[0].confidenceScores;
    const scorePOINT = "正向指數:"+score.positive+"\n 中立指數:"+score.neutral+"\n 負向指數:"+score.negative;
    
利用判斷式區分正向、中立、負向指標，並結合分數指標

    let reply = '';

    if(sentimentT == 'positive'){
      reply = '正向\n('+ scorePOINT +')' ;
    }else if(sentimentT == 'neutral'){
      reply = '中立\n('+scorePOINT+')';
    }else{
      reply = '負向\n('+scorePOINT+')';
    };
   
   
替換回應中的程式碼為自訂義

    const echo = {
      type: 'text',
      text: reply
    };
    
    

## Task-3 ##

根據文字訊息，找出主詞
    
    const sopt = results[0].sentences[0].opinions[0].target.text;
    
    
    

![Task3](https://github.com/emeraldChung/LAT/blob/main/Homework4/task3.jpg)



## Task-3.1 ##

透過分析主詞做出制式回復


    let reply = '';

    if(sentimentT == 'positive'){
      reply = '謝謝您給予的回饋，我們會繼續保持下去的';
    }else if(sentimentT == 'neutral'){
      reply = '謝謝您的回饋在' + sopt +'這部分問題，我們還會再加強';
    }else{
      reply = '很抱歉這次給予您不愉快的體驗，我們後續會再針對' + sopt + '這方面進行改善'
    };
    
    
 ![Task3.1](https://github.com/emeraldChung/LAT/blob/main/Homework4/task3.1.jpg)
