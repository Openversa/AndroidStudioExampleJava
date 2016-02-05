# AndroidStudioExampleJava
Example Android Studio Java accessing the Openversa Platform. This sameple android java application will enable you to test connections into the Openversa platform. Once you have an Openversa Account you will be able to create device credentials to place with the MainActivity.java file. Within the MainActivity.java file the code below will be altered to place in the new device credentials by your accounts. 

URL url = new URL("https://ovapi.openversa.com/v2/YOURCOMPANY/index.php");

                HttpsURLConnection connection = (HttpsURLConnection)url.openConnection();

                connection.setRequestMethod("POST");
                connection.setRequestProperty("Content-type", "application/x-www-form-urlencoded");

                String urlParameters = 
                "command=getMessages&username=“YOUR EMAIL”&appID=“YOUR MVA_ CODE”&appSecret=“YOUR APP SECRET”&
                groupID=“YOUR GROUP NUMBER”&logging=0";


                connection.setDoOutput(true);
                DataOutputStream wr = new DataOutputStream(connection.getOutputStream());
                wr.writeBytes(urlParameters);
                wr.flush();›
                wr.close();

                int responseCode = connection.getResponseCode();

                System.out.println("\nSending 'POST' request to URL : " + url);
                System.out.println("Post parameters : " + urlParameters);
                System.out.println("Response Code : " + responseCode);
                
[[images/AndroidSample.jpg]]
