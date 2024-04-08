FROM mcr.microsoft.com/devcontainers/anaconda:0-3

# Copy environment.yml (if found) to a temp location so we update the environment. Also
# copy "noop.txt" so the COPY instruction does not fail if no environment.yml exists.
COPY environment.yml* .devcontainer/noop.txt /tmp/conda-tmp/
RUN if [ -f "/tmp/conda-tmp/environment.yml" ]; then umask 0002 && /opt/conda/bin/conda env update -n base -f /tmp/conda-tmp/environment.yml; fi \
    && rm -rf /tmp/conda-tmp

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

WORKDIR /workdir

RUN apt-get update
RUN apt-get -y install locales && \
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm

RUN apt-get install -y vim less

RUN python -m pip install --upgrade pip
RUN python -m pip install --upgrade setuptools
RUN python -m pip install numpy
RUN python -m pip install distance
RUN python -m pip install geopy
RUN python -m pip install folium
RUN python -m pip install matplotlib
RUN python -m pip install japanize_matplotlib
#RUN python -m pip install geodesic
RUN python -m pip install tz
RUN python -m pip install datetime timedelta 
#timezone
#RUN python -m pip install random
#RUN python -m pip install pyplot
RUN python -m pip install polars
RUN python -m pip install selenium
#RUN python -m pip install webdriver_manager.chrome
#RUN python -m pip install selenium.webdriver.chrome.options
#RUN python -m pip install cv2

RUN python -m pip install jupyterlab