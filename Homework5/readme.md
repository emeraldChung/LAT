# HW5 #

## 電腦識別 ##

### 作業內容說明 ###

分析各式品牌的圖標，以此去判定該圖標是否有抄襲的可能，如圖

![圖例1](https://github.com/emeraldChung/LAT/blob/main/Homework5/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-05-30%20235815.png)

![圖例2](https://github.com/emeraldChung/LAT/blob/main/Homework5/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-05-31%20000131.png)

### 對於分析中可能的錯誤 ###

因為某些產品的圖標示慢慢演變而來，其中可能會和電腦分析相差有點遠因此有可能會無法偵測。


## 重點code ##

    var url = "https://eastus.api.cognitive.microsoft.com/";
      var uriBase = url + "vision/v2.1/analyze";
    
    var params = {
         "visualFeatures": "Objects,Faces,Brands,Categories,Description",
         "details": "Landmarks",
        "language": "zh",



    $("#responseTextArea").val(JSON.stringify(data, null, 2));
        $("#picDescription").empty();
        $("#picDescription").append("這圖標和"+data.brands[0].name+"相似，有抄襲的可能");
