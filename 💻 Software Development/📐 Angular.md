# Debugging frontend code in IntelliJ with breakpoints

1. Make sure chromium (or another supported browser) is configured in IntelliJ. All that's necessary is to point IntelliJ to the browser binary e.g. `/usr/bin/chromium`. To find the binary the command `whereis chromium` can be used on UNIX systems.
2. Launch application via run configuration (typically npm start) in debug mode.
3. Wait for the application to finish starting and `crtl+shift+click` on the url in the console. This launches a  browser that's already attached to IntelliJ. Breakpoints and other debugging features now work as expected.
