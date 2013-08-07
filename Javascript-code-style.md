http://javascript.crockford.com/code.html


If a function literal is anonymous, there should be one space between the word function and the ( (left parenthesis). If the space is omited, then it can appear that the function's name is function, which is an incorrect reading.

    div.onclick = function (e) {
        return false;
    };

    that = {
        method: function () {
            return this.datum;
        },
        datum: 0
    };
Use of global functions should be minimized.
