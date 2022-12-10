# fullScreen


```js
const fullScreen = {
    enter: (el) => {
        const docEl = el || document.documentElement
        if (docEl.requestFullscreen) {
            docEl.requestFullscreen()
        } else if (docEl.mozRequestFullScreen) {
            docEl.mozRequestFullScreen()
        } else if (docEl.webkitRequestFullscreen) {
            docEl.webkitRequestFullscreen()
        } else if (docEl.msRequestFullscreen) {
            docEl.msRequestFullscreen()
        }
    },
    exit: () => {
        if (document.exitFullScreen) {
            document.exitFullScreen();
        } else if (document.mozCancelFullScreen) {
            document.mozCancelFullScreen();
        } else if (document.webkitExitFullscreen) {
            document.webkitExitFullscreen();
        } else if (element.msExitFullscreen) {
            element.msExitFullscreen();
        }
    },
    isFull: () => {
        return (
            document.fullscreenElement ||
            document.mozFullScreenElement ||
            document.msFullScreenElement ||
            document.webkitFullscreenElement || null
        )
    },
    watch: (callback) => {
        window.addEventListener('resize', () => {
            callback(fullScreen.isFull())
        })
    }
}

export default fullScreen
```