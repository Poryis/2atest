# 2atest
```js
function bellFun() {
    var buttonNames = [
        { isPlaying: false, note: "Do", keyName: "1", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Jamalongassets%2FBells%2FDo.mp3?alt=media&token=090ee28e-224b-4d65-8eff-30230134831d" },
        { isPlaying: false, note: "Re", keyName: "2", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Bells%2FD%20-%20Re.mp3?alt=media&token=d3a97bc9-35dc-4604-9237-7189a0d933d56" },
        { isPlaying: false, note: "Mi", keyName: "3", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Bells%2FE%20-%20Mi.mp3?alt=media&token=4dec1284-93f1-4907-9aa2-8fe66a85c404" },
        { isPlaying: false, note: "Fa", keyName: "4", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Bells%2FF%20-%20Fa.mp3?alt=media&token=0b5efada-e3ea-440a-b918-7b0f068de04b" },
        { isPlaying: false, note: "So", keyName: "5", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Bells%2FG%20-%20So.mp3?alt=media&token=446a71af-813d-4781-92ac-dfa3f5d746ec" },
        { isPlaying: false, note: "La", keyName: "6", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Bells%2FA%20-%20La.mp3?alt=media&token=83b810af-709a-4f9f-a878-965912778b17" },
        { isPlaying: false, note: "Ti", keyName: "7", audioId: "https://firebasestorage.googleapis.com/v0/b/jelly-bells.appspot.com/o/Bells%2FB%20-%20ti.mp3?alt=media&token=59ed964a-1708-4dd8-bd6f-d7b04dca9cbb" },
    ];
    var timeout;

    function onKeyPress(event) {
        var currentBell = buttonNames.find((buttonType) => {
            return buttonType.keyName === event.key;
        });

        if (currentBell && !currentBell.isPlaying) {
            currentBell.isPlaying = true;
            cp.changeState(currentBell.note, "Down");
            var audio = new Audio(currentBell.audioId);
            audio.play();
        }
    }

    function onKeyUp(event) {
        var currentBell = buttonNames.find((buttonType) => {
            return buttonType.keyName === event.key;
        });

        if (currentBell) {
            currentBell.isPlaying = false;
            cp.changeState(currentBell.note, "Normal");
        }
    }

    window.addEventListener("keydown", onKeyPress);
    window.addEventListener("keyup", onKeyUp);
}

bellFun();
console("ready to test!");

```
