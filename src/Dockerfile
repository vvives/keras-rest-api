# MIT License
#
# Copyright (c) 2020 Víctor Vives Boix
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

FROM python:3.7.6

LABEL maintainer="vvives91@gmail.com"

# Install required system packages
RUN python -m pip install --upgrade pip

# Copy first requirements to use docker cache with dependencies
COPY requirements.txt ./app/requirements.txt

# Set current working directory to application folder
WORKDIR /app

# Install required application packages
RUN pip install -r requirements.txt

# Copy application data
COPY . /app

# Give permissions to the entrypoint bash file
RUN chmod +x ./entrypoint.sh

# Run python command
ENTRYPOINT ["/app/entrypoint.sh"]
