# resume
Resume in yaml format, pandoc'd into latex / pdf

sudo docker build -t pandocker .

sudo docker run --rm -t \
-v $(pwd):/workdir \
devintark/pandoc-resume:0.1 \
pandoc details.yml -o output/resume-3Oct21.pdf --template=resume.tex
