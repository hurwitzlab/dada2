#SINGULARITY = /usr/local/bin/singularity
SINGULARITY = /usr/local/src/singularity-2.5.1/bin/singularity
IMG_NAME = dada2.img
DEF_NAME = image.def
SIZE = 2048

run:
	sudo $(SINGULARITY) run $(IMG_NAME)

clean:
	rm -f $(IMG_NAME)

img: clean
	#sudo $(SINGULARITY) build $(IMG_NAME)
	sudo $(SINGULARITY) create --size $(SIZE) $(IMG_NAME)
	sudo $(SINGULARITY) bootstrap $(IMG_NAME) $(DEF_NAME)

shell:
	sudo $(SINGULARITY) shell --writable -B $(shell pwd):/home $(IMG_NAME)
