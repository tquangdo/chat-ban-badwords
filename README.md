![demo](demo.png)

# chat-ban-badwords
reactjs hook firebase

Badwords functions:
1/ auto change bardwords -> 🤐 I got BANNED for life for saying... ****: OK
2/ ban user for creating msg: NG
FB > Cloud Filestore > Security rules:


    function canCreateMessage(){
    	let isSignedIn = request.auth.id != null;
      let isOwner = request.auth.id == request.resource.data.uid;
      
      let isNotBanned = exists(
      	/databases/{database}/documents/banned/$(request.auth.id)
      ) == false;
      return isSignedIn && isOwner && isNotBanned;
    }
