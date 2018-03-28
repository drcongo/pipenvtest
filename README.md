# Test 1 - Let pipenv handle the virtualenv

    cd /vagrant/test1
    sudo apt install python3-pip --fix-missing
    sudo pip install --upgrade pip
    sudo pip3 install pipenv
    pipenv --three
    pipenv install


## Output

```
requirements.txt found, instead of Pipfile! Converting…
Warning: Your Pipfile now contains pinned versions, if your requirements.txt did.
We recommend updating your Pipfile to specify the "*" version, instead.
Pipfile.lock not found, creating…
Locking [dev-packages] dependencies…
Locking [packages] dependencies…
nv/utils.py", line 285, in actually_resolve_reps
    dep[len('-e '):]
  File "/usr/local/lib/python3.5/dist-packages/pipenv/vendor/pip9/req/req_install.py", line 144, in from_editable
    editable_req, default_vcs)
  File "/usr/local/lib/python3.5/dist-packages/pipenv/vendor/pip9/req/req_install.py", line 1197, in parse_editable
    "Could not detect requirement name, please specify one with #egg="
pip9.exceptions.InstallationError: Could not detect requirement name, please specify one with #egg=
```

# Test 2 - existing virtualenv

    cd /vagrant/test2
    virtualenv venv3 --no-site-packages
    pip3 install pipenv
    pipenv install


## Output

    requirements.txt found, instead of Pipfile! Converting…
    Warning: Your Pipfile now contains pinned versions, if your requirements.txt did.
    We recommend updating your Pipfile to specify the "*" version, instead.
    Pipfile.lock not found, creating…
    Locking [dev-packages] dependencies…
    Locking [packages] dependencies…
    e-packages/pipenv/utils.py", line 285, in actually_resolve_reps
        dep[len('-e '):]
      File "/vagrant/test2/venv3/lib/python3.5/site-packages/pipenv/vendor/pip9/req/req_install.py", line 144, in from_editable
        editable_req, default_vcs)
      File "/vagrant/test2/venv3/lib/python3.5/site-packages/pipenv/vendor/pip9/req/req_install.py", line 1197, in parse_editable
        "Could not detect requirement name, please specify one with #egg="
    pip9.exceptions.InstallationError: Could not detect requirement name, please specify one with #egg=


# Test 3 - install with pip into the venv

    pip install -r requirements.txt

## Output

    Obtaining django_admin_list_filter_dropdown from git+http://github.com/hactar-is/django-admin-list-filter-dropdown.git@1a5e6040dfeca6b09317401f5bd7a518141c9433#egg=django_admin_list_filter_dropdown (from -r requirements.txt (line 1))
      Cloning http://github.com/hactar-is/django-admin-list-filter-dropdown.git (to 1a5e6040dfeca6b09317401f5bd7a518141c9433) to ./venv3/src/django-admin-list-filter-dropdown
      Could not find a tag or branch '1a5e6040dfeca6b09317401f5bd7a518141c9433', assuming commit.
    Obtaining wagtail_eventbrite from git+git@codebasehq.com:hactar/hactar-library/wagtail_eventbrite.git@90bdfc680fc920eed8618d29aefac770d258c359#egg=wagtail_eventbrite (from -r requirements.txt (line 2))
      Cloning git@codebasehq.com:hactar/hactar-library/wagtail_eventbrite.git (to 90bdfc680fc920eed8618d29aefac770d258c359) to ./venv3/src/wagtail-eventbrite
    The authenticity of host 'codebasehq.com (185.22.208.213)' can't be established.
    ECDSA key fingerprint is SHA256:FdiEvTmXHY6bFGEnK7nTAjgMRCNe6K+CAWi6xiCi9Xo.
    Are you sure you want to continue connecting (yes/no)? yes
    Warning: Permanently added 'codebasehq.com,185.22.208.213' (ECDSA) to the list of known hosts.
    Kryptonite ▶ Requesting SSH authentication from phone
    Kryptonite ▶ Phone approval required. Respond using the Kryptonite app
    Kryptonite ▶ Success. Request Allowed ✔
      Could not find a tag or branch '90bdfc680fc920eed8618d29aefac770d258c359', assuming commit.
    Obtaining webassets from git+git://github.com/miracle2k/webassets.git@cc440911c6ac5f08fd98ea08442fe06e7a0aea2a#egg=webassets (from -r requirements.txt (line 3))
      Cloning git://github.com/miracle2k/webassets.git (to cc440911c6ac5f08fd98ea08442fe06e7a0aea2a) to ./venv3/src/webassets
      Could not find a tag or branch 'cc440911c6ac5f08fd98ea08442fe06e7a0aea2a', assuming commit.
    Collecting wagtail (from wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading wagtail-2.0-py3-none-any.whl (10.8MB)
        100% |████████████████████████████████| 10.8MB 157kB/s
    Collecting eventbrite (from wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading eventbrite-3.3.3-py2.py3-none-any.whl
    Collecting django-cron (from wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading django-cron-0.5.0.tar.gz
    Collecting wagtail-modelchooser (from wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading wagtail_modelchooser-2.0.0-py2.py3-none-any.whl
    Collecting beautifulsoup4<5.0,>=4.5.1 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading beautifulsoup4-4.6.0-py3-none-any.whl (86kB)
        100% |████████████████████████████████| 92kB 4.5MB/s
    Collecting django-treebeard<5.0,>=4.2.0 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading django-treebeard-4.2.1.tar.gz (310kB)
        100% |████████████████████████████████| 317kB 3.3MB/s
    Collecting Pillow<5.0,>=2.6.1 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading Pillow-4.3.0-cp35-cp35m-manylinux1_x86_64.whl (5.8MB)
        100% |████████████████████████████████| 5.8MB 246kB/s
    Collecting html5lib<1,>=0.999 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading html5lib-0.999999999-py2.py3-none-any.whl (112kB)
        100% |████████████████████████████████| 122kB 5.4MB/s
    Collecting Willow<1.2,>=1.1 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading Willow-1.1-py2.py3-none-any.whl (105kB)
        100% |████████████████████████████████| 112kB 6.8MB/s
    Collecting draftjs-exporter<2.1,>=2.0 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading draftjs_exporter-2.0.0.tar.gz
    Collecting django-taggit<1.0,>=0.22.2 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading django_taggit-0.22.2-py2.py3-none-any.whl (45kB)
        100% |████████████████████████████████| 51kB 8.9MB/s
    Collecting requests<3.0,>=2.11.1 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading requests-2.18.4-py2.py3-none-any.whl (88kB)
        100% |████████████████████████████████| 92kB 8.7MB/s
    Collecting django-modelcluster<5.0,>=4.0 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading django-modelcluster-4.1.tar.gz
    Collecting djangorestframework<4.0,>=3.1.3 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading djangorestframework-3.7.7-py2.py3-none-any.whl (1.1MB)
        100% |████████████████████████████████| 1.1MB 1.3MB/s
    Collecting Django<2.1,>=1.11 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading Django-2.0.3-py3-none-any.whl (7.1MB)
        100% |████████████████████████████████| 7.1MB 237kB/s
    Collecting Unidecode<1.0,>=0.04.14 (from wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading Unidecode-0.04.21-py2.py3-none-any.whl (228kB)
        100% |████████████████████████████████| 235kB 5.0MB/s
    Collecting django-common-helpers>=0.6.4 (from django-cron->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading django-common-helpers-0.9.1.tar.gz
    Collecting olefile (from Pillow<5.0,>=2.6.1->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading olefile-0.45.1.zip (112kB)
        100% |████████████████████████████████| 112kB 7.0MB/s
    Collecting six (from html5lib<1,>=0.999->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading six-1.11.0-py2.py3-none-any.whl
    Collecting webencodings (from html5lib<1,>=0.999->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading webencodings-0.5.1-py2.py3-none-any.whl
    Requirement already satisfied: setuptools>=18.5 in ./venv3/lib/python3.5/site-packages (from html5lib<1,>=0.999->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
    Collecting urllib3<1.23,>=1.21.1 (from requests<3.0,>=2.11.1->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading urllib3-1.22-py2.py3-none-any.whl (132kB)
        100% |████████████████████████████████| 133kB 5.7MB/s
    Requirement already satisfied: certifi>=2017.4.17 in ./venv3/lib/python3.5/site-packages (from requests<3.0,>=2.11.1->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
    Collecting chardet<3.1.0,>=3.0.2 (from requests<3.0,>=2.11.1->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading chardet-3.0.4-py2.py3-none-any.whl (133kB)
        100% |████████████████████████████████| 143kB 5.4MB/s
    Collecting idna<2.7,>=2.5 (from requests<3.0,>=2.11.1->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading idna-2.6-py2.py3-none-any.whl (56kB)
        100% |████████████████████████████████| 61kB 6.8MB/s
    Collecting pytz>=2015.2 (from django-modelcluster<5.0,>=4.0->wagtail->wagtail_eventbrite->-r requirements.txt (line 2))
      Downloading pytz-2018.3-py2.py3-none-any.whl (509kB)
        100% |████████████████████████████████| 512kB 2.6MB/s
    Building wheels for collected packages: django-cron, django-treebeard, draftjs-exporter, django-modelcluster, django-common-helpers, olefile
      Running setup.py bdist_wheel for django-cron ... done
      Stored in directory: /home/vagrant/.cache/pip/wheels/cf/80/2a/415455e8393c41ac88ec8d20f3a7509940212b9e1d49f96471
      Running setup.py bdist_wheel for django-treebeard ... done
      Stored in directory: /home/vagrant/.cache/pip/wheels/2b/b1/dd/268fdf638cdb9d1492d22b29c561268fce4762e5dfa5578229
      Running setup.py bdist_wheel for draftjs-exporter ... done
      Stored in directory: /home/vagrant/.cache/pip/wheels/65/0d/64/320aed55e7c8aeaaea3a602183b59e4f54aea2fd0f6be1f57e
      Running setup.py bdist_wheel for django-modelcluster ... done
      Stored in directory: /home/vagrant/.cache/pip/wheels/63/f9/25/42c10aafb86785a29e6132770fcd1cd21e20637712264c1ab1
      Running setup.py bdist_wheel for django-common-helpers ... done
      Stored in directory: /home/vagrant/.cache/pip/wheels/7a/6e/1c/583e181fbed881d468edc6168dcd6ac4001df254a973f23159
      Running setup.py bdist_wheel for olefile ... done
      Stored in directory: /home/vagrant/.cache/pip/wheels/75/f2/18/9f073aab5b308aaccec50c17d4afb33dffc3265254e7962d67
    Successfully built django-cron django-treebeard draftjs-exporter django-modelcluster django-common-helpers olefile
    Installing collected packages: django-admin-list-filter-dropdown, beautifulsoup4, pytz, Django, django-treebeard, olefile, Pillow, six, webencodings, html5lib, Willow, draftjs-exporter, django-taggit, urllib3, chardet, idna, requests, django-modelcluster, djangorestframework, Unidecode, wagtail, eventbrite, django-common-helpers, django-cron, wagtail-modelchooser, wagtail-eventbrite, webassets
      Running setup.py develop for django-admin-list-filter-dropdown
      Running setup.py develop for wagtail-eventbrite
      Running setup.py develop for webassets
    Successfully installed Django-2.0.3 Pillow-4.3.0 Unidecode-0.4.21 Willow-1.1 beautifulsoup4-4.6.0 chardet-3.0.4 django-admin-list-filter-dropdown django-common-helpers-0.9.1 django-cron-0.5.0 django-modelcluster-4.1 django-taggit-0.22.2 django-treebeard-4.2.1 djangorestframework-3.7.7 draftjs-exporter-2.0.0 eventbrite-3.3.3 html5lib-0.999999999 idna-2.6 olefile-0.45.1 pytz-2018.3 requests-2.18.4 six-1.11.0 urllib3-1.22 wagtail-2.0 wagtail-eventbrite wagtail-modelchooser-2.0.0 webassets webencodings-0.5.1
