# Open-XML-Files-and-Download-


import requests as rq
import pandas as pd
data=pd.read_excel('U.xlsx')
#a1=data.iloc[:,0].values
x=0
for x in range(0,1844):
     
        Z=(data['Urls'][x])
        #url_access()
        #from urllib.parse import quote
        from requests.auth import HTTPBasicAuth
#    user= quote('UserID')
#    pwd = quote('Password')
        response = rq.get(Z, auth=HTTPBasicAuth('Maharasu', 'Indira@000'))

#url = "Put the URL"
 
        if response.status_code != 200: 
           print('Status:', response.status_code, 'Headers:', response.headers, 'Error Response:',response.json())
           exit() 
        else :
           print ("Successful Connection!!!")
           q = x
           filename = "y" + str(q) + ".xml"
        
           with open(filename, 'wb') as file:
        
                    file.write(response.content)
    
        x+=1
    
    
    

    
