# monkeyDugiWiki
개발 위키
```java
// 1. 멜론의 가수, 제목, 순위와 youtubeAPI의 videoId, image를 List<requestDto>에 담는다.
// 2. loob를 돌며, Dto에서 toEntity를 만들어 Entity를 생성하고 save 한다.
// 3. 끝!


package apiTest;

import org.json.JSONArray;
import org.json.JSONException;
import org.json.JSONObject;

public class Api1 {
	public static void main(String[] args) {
        String jsonString = "{'kind': 'aaaa','items': [{'kind': 'youduresil','id': {'kind': 'youtudvid','videoId': 'gesidkw123'},'snippet': {'title': 'BTS방탄의 노래들','dscription': '방탄 설명 글','thumbnails': {'default': {'url': 'imgaUrlDefault.jpg','width': 120,'height': 90},'medium':{'url': 'imgaUrlmedium.jpg','width': 320,'height': 180},'high': {'url': 'imgaUrlHigh.jpg','width': 480,'height': 360}},'channelTitle': 'Bic Hit Labels','liveBroadCastContent': 'none'}},{'kind': 'youduresil222','id': {'kind': 'youtudvid222','videoId': 'gesidkw123222'},'snippet': {'title': 'BTS방탄의 노래들222','dscription': '방탄 설명 글222','thumbnails': {'default': {'url': 'imgaUrlDefault.jpg222','width': 120222,'height': 90222},'medium':{'url': 'imgaUrlmedium.jpg222','width': 320222,'height': 180222},'high': {'url': 'imgaUrlHigh.jpg222','width': 480222,'height': 360222}},'channelTitle': 'Bic Hit Labels222','liveBroadCastContent': 'none222'}}   ]}";

        try
        {
            JSONObject jsonObject = new JSONObject(jsonString);
            JSONArray items = jsonObject.getJSONArray("items");
            
            for(int i = 0; i < items.length(); i++) {            	            
	            JSONObject item0 = items.getJSONObject(i);
	            
	            JSONObject id = item0.getJSONObject("id");
	            String videoId = id.getString("videoId");
	            
	            JSONObject snippet = item0.getJSONObject("snippet");
	            
	            String title = snippet.getString("title");
	            
	            JSONObject thumbnails = snippet.getJSONObject("thumbnails");
	            
	            JSONObject defaul = thumbnails.getJSONObject("default");
	            
	            String url = defaul.getString("url");
	            
	            System.out.println("title : " + title);
	            System.out.println("videoId : " + videoId);
	            System.out.println("url : " + url);
	            
	            System.out.println("===================================================");
            }
        } catch (JSONException e) {
            e.printStackTrace();
        }
	}
}
```
