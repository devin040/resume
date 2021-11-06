
# Pandoc'd Resume
This is my resume in yaml format, pandoc'd into latex / pdf. 

The intent was to separate the content layer of the resume from the presentation layer. So I could easily update the plain text content of it
without worrying about the layout / display / typsetting.


## Installation

This repo includes a Dockerfile image (also available from [Docker Hub](https://hub.docker.com/repository/docker/devintark/pandoc-resume)) to keep it platform agnostic, and to allow me to not worry about which tex environment, fonts, versions are installed on the local machine. Admittedly, this results in a pretty hefty docker image, which I need to work on. 

To build the docker file

```bash
sudo docker build -t <image-name> .
```


## Usage

To use, update the details.yml file with the information you want in the resume.

If required, e.g. you want different fields in the resume, update the resume.tex file (the LaTeX template that the information from the yaml file will be inserted into).

Then run

```bash
sudo docker run --rm -it \
-v $(pwd):/workdir \
repo/image:tag \
pandoc details.yml -o output/resume-<date>.pdf --template=resume.tex
```

On Windows, pwd works a bit different:
```pwsh
docker run --rm -it -v ${PWD}:/workdir devintark/pandoc-resume pandoc details.yml -o output/NAME.pdf --template=resume.tex
```

## Contributing
Feel free to fork for yourself, but probably not accepting contributions at this time!

## License
[MIT](https://choosealicense.com/licenses/mit/)

