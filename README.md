# sharejeeni
# This package helps to download files from sharepoint site using client id , client secret and tenant id via Azure Active Directory.  

- First You need to register an App on Azure Active Directory and get tenant id , client id and client secret.

- Also you need sharepoint site domain name and site url.

 Code Eg:

    from sharejeeni import request_token, get_file

        sharepoint_url =  "https://xxxx.sharepoint.com"
        client_id = "3b724c43-7f32-4d6d-861f-xxxx"
        client_secret = "5yB8Q~xxxxxxxxxxxxxxx"
        tenant_id = 'b71957ca-e23b-4df6-b963-xxxxxx'

        Site_name = 'TrialSite' # sharepoint site name
        domain = 'xxxx.sharepoint.com'

        folder = 'Trial_Folder' #Folder name
        file = "subfile.csv" #File name


    token = request_token(tenant_id,client_secret,client_id) # call request_token function to get the token

    get_file(token,Site_name,domain,folder,file) # call get_file function to get the file
