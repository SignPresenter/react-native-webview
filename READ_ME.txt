1. Extract file in one directory.
2. install example apk using below command
	"npx run-android" or "npm run-android" (without quotes)
3. start react-native using below command
	"react-native start" (once js bundle pushed)
4. To test app open NativeWebpage.tsx from below steps. 
	1. Go to root directory of project -> example\examples -> open NativeWebpage.tsx file
	2. in this file example is added. you can test by changing url, and logic inside onInterceptCallback



//onInterceptCallback function

onInterceptCallback={(e) =>{
	e is nativeEvent object which returns obj mentioned below
	
	const {nativeEvent} = e;
	
	nativeEvent return object
	const {mimetype, file (base64), header:{origin, referral, accept,url,... }, method, url} = nativeEvent
	
	return {
			mimetype: String Required
			file:String (Base 64) Required //if not available then pass default file from nativeEvent
			url:String Required  //if not available then pass default url from nativeEvent
			cache:Boolean Optional //to save locally set to true,
			offline:Boolean  Optional //to display file if available offline
		}

}}


