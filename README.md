# Adding mimetype icon for Nim-lang to Ubuntu

## Clone/fork Yaru repo

* **Clone** Yaru repo, if you just would like to test experiments:

	```
	git clone https://github.com/ubuntu/yaru.git
	```
* **Fork** Yaru repo, if you want to make a pull request:
	1. Click on the **Fork** button at the top right corner of [Yaru repo](https://github.com/ubuntu/yaru).
	2. Clone your fork running the command:
		```
		git clone https://github.com/YOUR_USERNAME/yaru.git
		```

## Create Nim template icons

1. Open wit [Inkscape](https://inkscape.org) an *.svg* template from `~/yaru/icons/src/fullcolor/mimetypes` and name it **text-x-nim.svg**.
1. Select ***Layers → Layers*** and click the eye next to the layer called **Baseplate** to make it visible.
1. Change the mimetypes so that will show **text-x-nim**.
1. Click again the eye next to the layer called **Baseplate** to make it NOT visible.
1. After you have finished to edit the template, save it and close Inkscape.

## Generating png files

1. Move to `~/yaru/icons/src/fullcolor/` directory and run the **render-bitmaps.py** script:
	```
	cd yaru/icons/src/fullcolor/
	./render-bitmaps.py applications-apk text-x-nim
	```
1. Initialize build system:
	```
	cd ~/yaru
	meson build
	```
1. Build and install:
	```
	sudo ninja install
	```
All Nim *.png* icons will now appear into the following forlders:
* system folder: `/usr/share/icons/Yaru`;
* local repo folder: `~/yaru/icons/Suru`.

## Generating symlinks

1. Open with a text editor the `~/yaru/icons/src/symlinks/fullcolor/mimetypes.list` file.
1. Find the section where the strings begin with;
	```
	text-x-
	```
	and add the string:
	```
	text-x-nim.png text-nim.png
	```
1. Run the **generate-symlinks.sh** script:
	```
	cd ~/yaru/icons/src/symlinks/
	./generate-symlinks.sh -m text-x-nim
	```
1. Install the changes:
	```
	cd ~/yaru/build
	sudo ninja install
	```




