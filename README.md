STAR_COUNT_GITHUB
====

This repository is the Star Count over time of github repositories

## Step for Run Code

    1. download anaconda that suitable with your OS following this link: https://docs.anaconda.com/anaconda/install/index.html
    2. install anaconda
    3. click run Notebook
    4. open star_count_github folder that you clone from github then open "star_count_github.ipynb" then you can press "shift+enter" for see the result

## Detail in Code

* datasets(output) is dataframe 
* you can add columns for dataframe by 
    ```df = pd.DataFrame(columns=['column_name_1','column_name_2','column_name_3',...,'column_name_n']```
    and
    <pre>for repo in results['items']:
            data = {'column_name_1': repo['response_key_value_1'],
               'column_name_2': repo['response_key_value_2'],
               'column_name_3': repo['response_key_value_3'],
                ...
               'column_name_n': repo['response_key_value_n']}
            df = df.append(data, ignore_index=True)
    </pre>
    ps. response_key_value_n is response that you get from request API command (ref: https://docs.github.com/en/rest/guides/getting-started-with-the-rest-api)

* github search API: (ref: https://docs.github.com/en/rest/reference/search)
    for example: ```results = requests.get('https://api.github.com/search/repositories?q=language:python&per_page=50').json()```
    - q=language:python : langauge that you want to query in public github repositories is python language
    - per_page=50 : result per page is 50 repositories
