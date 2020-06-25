# Quetz

## Usage

Create environment:
```
mamba create -n quetz -c conda-forge python fastapi authlib httpx=0.12.0 sqlalchemy sqlite \
python-multipart uvicorn conda-build

conda activate quetz
```

Initialize environment variables:
```
source ./set_env_dev.sh
```

Initialize test database:
```
python init_db.py
```

Run the fastapi server:
```
uvicorn quetz.main:app --reload
```

Links:
 * http://localhost:8000/static - Login with your github account
 * http://localhost:8000/dummylogin/[ alice | bob | carol | dave] - Login with test user
 * http://localhost:8000/docs - Swagger UI for this REST service

Download `xtensor` as test package:
```
./download-test-package.sh
```

Run test upload CLI client:
```
./test-cli-client.sh
```

Install the test package with conda:
```
mamba install -c http://localhost:8000/static/channels/channel0 -c conda-forge xtensor
```

Output:
```
...
  Package  Version  Build          Channel                                                     Size
─────────────────────────────────────────────────────────────────────────────────────────────────────
  Install:
─────────────────────────────────────────────────────────────────────────────────────────────────────

  xtensor   0.16.1  0              http://localhost:8000/static/channels/channel0/osx-64     109 KB
  xtl       0.4.16  h04f5b5a_1000  conda-forge/osx-64                                         47 KB

  Summary:

  Install: 2 packages

  Total download: 156 KB

─────────────────────────────────────────────────────────────────────────────────────────────────────
...
```

Browse channels:
```
http://localhost:8000/static/channels/channel0/
```

## License

We use a shared copyright model that enables all contributors to maintain the copyright on their contributions.

This software is licensed under the BSD-3-Clause license. See the [LICENSE](LICENSE) file for details.
