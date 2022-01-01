![Main_Image](https://developer.spotify.com/assets/branding-guidelines/logo@2x.png)

## Whats is SpotiCheck?  
SpotiCheck is an account checker for the **Spotify** stream music service written in **Python 2.7**. SpotiCheck manages to evade the **Spotify** *security system* that prevents the check of accounts massively. The **Spotify** *security system* is simply a **CSRF token**, a system implemented by many pages to avoid checking accounts on theirs platform but this *security system* is not very secure. Not enough for a company like **Spotify**. **SpotiCheck is a challenge between friends and with the intention of educating so it should not be used to commit any type of crime that will be committed under the responsibility of the user of the program not the creator of the same**.  

## How does its works?  
Obviously with some magic and a bit of Matrix shit. Nah just kidding.    
SpotiCheck uses as a main base the module of `requests` to make requests to different parts of **Spotify**. The first thing you get is the CSRF token which is obtained at **accounts.spotify.com** for later use in the login API hosted at **accounts.spotify.com/api/login** with the username, password, etc ... Depending on the parameters of the API response the user and password will be correct or incorrect. If they are correct, a request will be created to **spotify.com/de/account/overview/** to get more information about the account.  

## Installation

Install python-pip and run this command from the SpotiCheck directory
```
pip install -r requeriments.txt
```

## Help Message  
```
usage: SpotiCheck.py [-h] [--output_type OUTPUT_TYPE] [--threads THREADS]
                    [--nothreads]
                    combo_list output_file_name

positional arguments:
  combo_list            The combo list is a list with users and passwords in a
                        'username:password' format.
  output_file_name      Only the name of the file. The extension will be
                        determined by the type of output selected.

optional arguments:
  -h, --help            show this help message and exit
  --output_type OUTPUT_TYPE
                        The output type can be: txt, json, xml and html
                        (Default: txt).
  --threads THREADS     Number of workers that SpotCheck uses (A very high
                        number can cause an error in the program due to the
                        limitations of your computer) (Default: 4).
  --nothreads           If this argument is specified, SpotCheck will not
                        create any thread, otherwise the main SpotCheck
                        process will perform the checks.
```
