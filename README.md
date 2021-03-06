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
	cd ~/yaru/icons/src/fullcolor/
	./render-bitmaps.py text-x-nim
	```
1. Initialize build system:
	```
	cd ~/yaru
	meson build
	```
1. Build and install:
	```
	cd ~/yaru/build
	sudo ninja install
	```
All Nim *.png* icons will now appear into the following forlders:
* system folder: `/usr/share/icons/Yaru`;
* local repo folder: `~/yaru/icons/Suru`.

## Pull request

1. Run the following commands:
	```
	cd ~/yaru
	git add .
	git commit -a -m "write_a_message"
	```
1. On GitHub select you Yaru-fork page
1. Click on **Pull requestes** link (top left corner).
1. Click on the **Create pull request** green button.
