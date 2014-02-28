SONetworking
============

Networking Static Library  (for Windows phone 7.1)

USAGE
=====

Add all *.dll file in SONetworking/Bin/Release/ to your project's references. 

Add SONetworking to using list.

<pre>
using SONetworking;
</pre>

Example of how to get facebook's user info
<pre>
      SOJsonRequestOperation.BaseUrl = "https://graph.facebook.com/";

      List<KeyValuePair<string,string>> parameters = new List<KeyValuePair<string, string>>();
      parameters.Add(new KeyValuePair<string, string>("access_token", "_your_fb_access_token_"));

      SOJsonRequestOperation.StartJSONRequestOperation(HttpMethod.Get, "me",parameters,
          delegate(bool success, int statusCode, JObject fbObject)
          {
              if (success)
              {
                  MessageBox.Show(fbObject["name"].ToString());
              }
          });
</pre>
