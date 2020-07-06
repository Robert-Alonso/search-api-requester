# MLSearch Libraries

The mlsearch libraries are a collection of libraries that work as a wrapper over other repositories for fetching the data required for MLSearch Engine.

The package can be installed running `python setup.py` inside the project folder.

<hr>
<b>Standalone usage (CLI)</b>

`mlsearch -q query -i start_index -c number_of_result -s source`

For example
`mlsearch -q "cnn" -i 0 -c 3 -s "github"`

Available Parameters:
```
  -h, --help            show this help message and exit

Required Parameters:

  -q QUERY, --query QUERY
                        Keyword for searching.
  -i INIT_IDX, --init_idx INIT_IDX
                        Initial index for pagination.
  -c COUNT, --count COUNT
                        Total number of results to be fetched.
  -s SOURCE, --source SOURCE
                        Source API to be looking for.
  -ck COOKIES, --cookies COOKIES
                        Cookies of current user.
  -tm TIMESTAMP, --timestamp TIMESTAMP
                        Timestamp of requesting API.
Optional Parameters:

  -pu PWC_USER, --pwc_user PWC_USER
                        Paper with code repository user name.
  -pp PWC_PASSWORD, --pwc_password PWC_PASSWORD
                        Paper with code repository password.
  -gt GITHUB_ACC_TOKEN, --github_acc_token GITHUB_ACC_TOKEN
                        Github access token.
  -yk YOUTUBE_DEV_KEY, --youtube_dev_key YOUTUBE_DEV_KEY
                        Youtube developer key.
  -ynpt NEXT_PAGE_TOKEN, --y_next_page_token NEXT_PAGE_TOKEN
                        Next page token for Youtube API.
  -yo Y_QUERY_ORDER, --y_query_order Y_QUERY_ORDER
                        Youtube Query Order.
```

<hr>
<b>Using as an API<b>
<br>

```python
from mlsearch.api_requester import APIRequest

api_request = APIRequest(source, query, 
    init_idx, count)
api_request.pwc_auth_info = ('user_name', 'password')
api_request.github_acc_token = 'token'
api_request.youtube_developer_key = 'your_key'
```

## Development setup

Create a new virtual environment and install the required python libraries into it:

<!-- TODO: confirm if the version used is python 3.7 -->
<!-- TODO: would be nice to include an isort and black auto formatting pipeline 
           through a makefile, as well as pylint and mypy checks -->

```bash
virtualenv --python=python3.7 venv
source venv/bin/activate
pip install -r requirements.txt
```
