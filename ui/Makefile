all: init build-web build-capacitor android-sync

clean:
	git clean -fxd

init:
	npm ci

generate-pwa-assets:
	npx pwa-assets-generator

test:
	#npx tsc && npx jest
	@echo "\033[31mThis is broken now: SecurityError: Cannot initialize local storage without a --localstorage-file path\033[0m"

dev:
	MODE= npx vite --host

preview:
	make build-web
	MODE= npx vite preview --host

build:
	make test && \
		npx vite build --minify -c vite.config.js --emptyOutDir

build-web:
	MODE= make build

build-capacitor:
	MODE=capacitor make build

android-sync:
	npx cap sync android
	@echo '--> Open Android Studio with `make android-open`'

android-open:
	npx cap open android
