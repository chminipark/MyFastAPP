Installation

``` bash
# IN CLI
# clone MyFastAPI 
git clone https://github.com/chminipark/MyFastAPP.git

# check current path "MyFastApp/." and continue installation
cd MyFastApp

# clone AnimatedDrawings and add rest_api dependency
# build docker-compose
git clone https://github.com/facebookresearch/AnimatedDrawings.git
cp -R AnimatedDrawings/examples AnimatedDrawings/rest_api
cp animated_drawings_docker/animated_drawings_api.py AnimatedDrawings/rest_api
docker-compose up -d

# MODIFY CODE
# AnimatedDrawings/rest_api/image_to_annotations.py, line 51, 85
# replace localhost -> torchserve

# AnimatedDrawings/animated_drawings/mvc_base_cfg.yaml, line 12
# USE_MESA: True -> USE_MESA: False
```

Test
``` bash
http://localhost:12/test_docker_network

# GET
# AnimatedDrawings test ping success!!
```