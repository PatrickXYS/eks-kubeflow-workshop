# Copyright 2019 The Kubeflow Authors
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
FROM ubuntu:16.04

RUN apt-get update -y && \
    apt-get install --no-install-recommends -y -q ca-certificates python-dev python-setuptools wget && \
    easy_install pip && \
    pip install pyyaml==3.12 kubernetes

RUN mkdir /ml && \
    wget https://raw.githubusercontent.com/kubeflow/pipelines/master/components/kubeflow/launcher/src/launch_tfjob.py && \
    cp launch_tfjob.py /ml

ENTRYPOINT ["python", "/ml/launch_tfjob.py"]