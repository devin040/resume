# resume
Resume in yaml format, pandoc'd into latex / pdf

sudo docker build -t pandocker .

sudo docker run --rm -t \
-v $(pwd):/workdir \
pandocker \
pandoc details.yml -o output/resume.pdf --template=resume.tex
