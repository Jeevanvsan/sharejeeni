# sharejeeni
# This package helps to download files from sharepoint site using client id , client secret and tenant id via Azure Active Directory. 

- First You need to register an App on Azure Active Directory and get tenant id , client id and client secret.

- Also you need sharepoint site domain name and site url.

# Install package
 pip install sharejeeni

 Code Eg:

    import sharejeeni

        client_id = "xxxx-xxx-xxx-xxx-xxxx"
        client_secret = "xxxxxxxxxxxxxxx"
        tenant_id = 'xx-xx-xx-xxx-xxxxxx'
        
        sharepoint_url =  "https://xxxx.sharepoint.com"
        Site_name = 'TrialSite' # sharepoint site name
        domain = 'xxxx.sharepoint.com'

        folder = 'Trial_Folder' #Folder name
        subfolder = 'SubTrial_Folder' #Subfolder name
        file = "subfile.csv" #File name
        save_as = 'savedfile.csv' 


    token = sharejeeni.request_token(tenant_id,client_secret,client_id)

    site = sharejeeni.get_site(token,Site_name,domain)

    sharejeeni.Get().file(file,token,site,save_as)

# for file inside folder

    sharejeeni.Get().folder(folder).file(file,token,site,save_as)

# for file in subfolders

    sharejeeni.Get().folder(folder).subfolder(subfolder).file(file,token,site,save_as)
