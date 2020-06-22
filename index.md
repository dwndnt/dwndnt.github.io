<html lang="en-US"><head prefix="og: http://ogp.me/ns# book: http://ogp.me/ns/book#">
        
        <meta charset="UTF-8">
        <title>MD5 Hash | CTF Resources</title>

        <meta content="text/html; charset=utf-8" http-equiv="Content-Type">
        <meta name="robots" content="index, follow">
        <meta name="author" content="ctfs">
        <meta name="description" content="This repository aims to be an archive of information, tools, and references regarding CTF competitions.">
        <meta name="keywords" content="gitbook,github">
        <meta name="generator" content="www.gitbook.io">

        
        <link rel="next" href="../../../topics/cryptography/rsa/README.html">
        
        
        <link rel="prev" href="../../../topics/cryptography/vigenere-cipher/README.html">
        

        <meta property="og:title" content="MD5 Hash | CTF Resources">
        <meta property="og:site_name" content="CTF Resources">
        <meta property="og:type" content="book">
        <meta property="og:locale" content="en_US">

        <meta property="book:author" content="https://github.com/ctfs">
        <meta property="book:tag" content="GitBook">

        <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
        <meta name="apple-mobile-web-app-capable" content="yes">
        <meta name="apple-mobile-web-app-status-bar-style" content="black">

        <link rel="shortcut icon" href="../../../gitbook/images/favicon.ico" type="image/x-icon">
        
    <style id="ace_editor">.ace_editor {position: relative;overflow: hidden;font-family: 'Monaco', 'Menlo', 'Ubuntu Mono', 'Consolas', 'source-code-pro', monospace;font-size: 12px;line-height: normal;direction: ltr;}.ace_scroller {position: absolute;overflow: hidden;top: 0;bottom: 0;background-color: inherit;-ms-user-select: none;-moz-user-select: none;-webkit-user-select: none;user-select: none;}.ace_content {position: absolute;-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;cursor: text;min-width: 100%;}.ace_dragging, .ace_dragging * {cursor: move !important;}.ace_dragging .ace_scroller:before{position: absolute;top: 0;left: 0;right: 0;bottom: 0;content: '';background: rgba(250, 250, 250, 0.01);z-index: 1000;}.ace_dragging.ace_dark .ace_scroller:before{background: rgba(0, 0, 0, 0.01);}.ace_selecting, .ace_selecting * {cursor: text !important;}.ace_gutter {position: absolute;overflow : hidden;width: auto;top: 0;bottom: 0;left: 0;cursor: default;z-index: 4;-ms-user-select: none;-moz-user-select: none;-webkit-user-select: none;user-select: none;}.ace_gutter-active-line {position: absolute;left: 0;right: 0;}.ace_scroller.ace_scroll-left {box-shadow: 17px 0 16px -16px rgba(0, 0, 0, 0.4) inset;}.ace_gutter-cell {padding-left: 19px;padding-right: 6px;background-repeat: no-repeat;}.ace_gutter-cell.ace_error {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAABOFBMVEX/////////QRswFAb/Ui4wFAYwFAYwFAaWGAfDRymzOSH/PxswFAb/SiUwFAYwFAbUPRvjQiDllog5HhHdRybsTi3/Tyv9Tir+Syj/UC3////XurebMBIwFAb/RSHbPx/gUzfdwL3kzMivKBAwFAbbvbnhPx66NhowFAYwFAaZJg8wFAaxKBDZurf/RB6mMxb/SCMwFAYwFAbxQB3+RB4wFAb/Qhy4Oh+4QifbNRcwFAYwFAYwFAb/QRzdNhgwFAYwFAbav7v/Uy7oaE68MBK5LxLewr/r2NXewLswFAaxJw4wFAbkPRy2PyYwFAaxKhLm1tMwFAazPiQwFAaUGAb/QBrfOx3bvrv/VC/maE4wFAbRPBq6MRO8Qynew8Dp2tjfwb0wFAbx6eju5+by6uns4uH9/f36+vr/GkHjAAAAYnRSTlMAGt+64rnWu/bo8eAA4InH3+DwoN7j4eLi4xP99Nfg4+b+/u9B/eDs1MD1mO7+4PHg2MXa347g7vDizMLN4eG+Pv7i5evs/v79yu7S3/DV7/498Yv24eH+4ufQ3Ozu/v7+y13sRqwAAADLSURBVHjaZc/XDsFgGIBhtDrshlitmk2IrbHFqL2pvXf/+78DPokj7+Fz9qpU/9UXJIlhmPaTaQ6QPaz0mm+5gwkgovcV6GZzd5JtCQwgsxoHOvJO15kleRLAnMgHFIESUEPmawB9ngmelTtipwwfASilxOLyiV5UVUyVAfbG0cCPHig+GBkzAENHS0AstVF6bacZIOzgLmxsHbt2OecNgJC83JERmePUYq8ARGkJx6XtFsdddBQgZE2nPR6CICZhawjA4Fb/chv+399kfR+MMMDGOQAAAABJRU5ErkJggg==");background-repeat: no-repeat;background-position: 2px center;}.ace_gutter-cell.ace_warning {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAAAmVBMVEX///8AAAD///8AAAAAAABPSzb/5sAAAAB/blH/73z/ulkAAAAAAAD85pkAAAAAAAACAgP/vGz/rkDerGbGrV7/pkQICAf////e0IsAAAD/oED/qTvhrnUAAAD/yHD/njcAAADuv2r/nz//oTj/p064oGf/zHAAAAA9Nir/tFIAAAD/tlTiuWf/tkIAAACynXEAAAAAAAAtIRW7zBpBAAAAM3RSTlMAABR1m7RXO8Ln31Z36zT+neXe5OzooRDfn+TZ4p3h2hTf4t3k3ucyrN1K5+Xaks52Sfs9CXgrAAAAjklEQVR42o3PbQ+CIBQFYEwboPhSYgoYunIqqLn6/z8uYdH8Vmdnu9vz4WwXgN/xTPRD2+sgOcZjsge/whXZgUaYYvT8QnuJaUrjrHUQreGczuEafQCO/SJTufTbroWsPgsllVhq3wJEk2jUSzX3CUEDJC84707djRc5MTAQxoLgupWRwW6UB5fS++NV8AbOZgnsC7BpEAAAAABJRU5ErkJggg==");background-position: 2px center;}.ace_gutter-cell.ace_info {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAAAAAA6mKC9AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAAJ0Uk5TAAB2k804AAAAPklEQVQY02NgIB68QuO3tiLznjAwpKTgNyDbMegwisCHZUETUZV0ZqOquBpXj2rtnpSJT1AEnnRmL2OgGgAAIKkRQap2htgAAAAASUVORK5CYII=");background-position: 2px center;}.ace_dark .ace_gutter-cell.ace_info {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQBAMAAADt3eJSAAAAJFBMVEUAAAChoaGAgIAqKiq+vr6tra1ZWVmUlJSbm5s8PDxubm56enrdgzg3AAAAAXRSTlMAQObYZgAAAClJREFUeNpjYMAPdsMYHegyJZFQBlsUlMFVCWUYKkAZMxZAGdxlDMQBAG+TBP4B6RyJAAAAAElFTkSuQmCC");}.ace_scrollbar {position: absolute;right: 0;bottom: 0;z-index: 6;}.ace_scrollbar-inner {position: absolute;cursor: text;left: 0;top: 0;}.ace_scrollbar-v{overflow-x: hidden;overflow-y: scroll;top: 0;}.ace_scrollbar-h {overflow-x: scroll;overflow-y: hidden;left: 0;}.ace_print-margin {position: absolute;height: 100%;}.ace_text-input {position: absolute;z-index: 0;width: 0.5em;height: 1em;opacity: 0;background: transparent;-moz-appearance: none;appearance: none;border: none;resize: none;outline: none;overflow: hidden;font: inherit;padding: 0 1px;margin: 0 -1px;text-indent: -1em;-ms-user-select: text;-moz-user-select: text;-webkit-user-select: text;user-select: text;}.ace_text-input.ace_composition {background: #f8f8f8;color: #111;z-index: 1000;opacity: 1;text-indent: 0;}.ace_layer {z-index: 1;position: absolute;overflow: hidden;white-space: pre;height: 100%;width: 100%;-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;/* setting pointer-events: auto; on node under the mouse, which changesduring scroll, will break mouse wheel scrolling in Safari */pointer-events: none;}.ace_gutter-layer {position: relative;width: auto;text-align: right;pointer-events: auto;}.ace_text-layer {font: inherit !important;}.ace_cjk {display: inline-block;text-align: center;}.ace_cursor-layer {z-index: 4;}.ace_cursor {z-index: 4;position: absolute;-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;border-left: 2px solid}.ace_slim-cursors .ace_cursor {border-left-width: 1px;}.ace_overwrite-cursors .ace_cursor {border-left-width: 0px;border-bottom: 1px solid;}.ace_hidden-cursors .ace_cursor {opacity: 0.2;}.ace_smooth-blinking .ace_cursor {-moz-transition: opacity 0.18s;-webkit-transition: opacity 0.18s;-o-transition: opacity 0.18s;-ms-transition: opacity 0.18s;transition: opacity 0.18s;}.ace_editor.ace_multiselect .ace_cursor {border-left-width: 1px;}.ace_marker-layer .ace_step, .ace_marker-layer .ace_stack {position: absolute;z-index: 3;}.ace_marker-layer .ace_selection {position: absolute;z-index: 5;}.ace_marker-layer .ace_bracket {position: absolute;z-index: 6;}.ace_marker-layer .ace_active-line {position: absolute;z-index: 2;}.ace_marker-layer .ace_selected-word {position: absolute;z-index: 4;-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;}.ace_line .ace_fold {-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;display: inline-block;height: 11px;margin-top: -2px;vertical-align: middle;background-image:url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABEAAAAJCAYAAADU6McMAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAJpJREFUeNpi/P//PwOlgAXGYGRklAVSokD8GmjwY1wasKljQpYACtpCFeADcHVQfQyMQAwzwAZI3wJKvCLkfKBaMSClBlR7BOQikCFGQEErIH0VqkabiGCAqwUadAzZJRxQr/0gwiXIal8zQQPnNVTgJ1TdawL0T5gBIP1MUJNhBv2HKoQHHjqNrA4WO4zY0glyNKLT2KIfIMAAQsdgGiXvgnYAAAAASUVORK5CYII="),url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAA3CAYAAADNNiA5AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAACJJREFUeNpi+P//fxgTAwPDBxDxD078RSX+YeEyDFMCIMAAI3INmXiwf2YAAAAASUVORK5CYII=");background-repeat: no-repeat, repeat-x;background-position: center center, top left;color: transparent;border: 1px solid black;-moz-border-radius: 2px;-webkit-border-radius: 2px;border-radius: 2px;cursor: pointer;pointer-events: auto;}.ace_dark .ace_fold {}.ace_fold:hover{background-image:url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABEAAAAJCAYAAADU6McMAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAJpJREFUeNpi/P//PwOlgAXGYGRklAVSokD8GmjwY1wasKljQpYACtpCFeADcHVQfQyMQAwzwAZI3wJKvCLkfKBaMSClBlR7BOQikCFGQEErIH0VqkabiGCAqwUadAzZJRxQr/0gwiXIal8zQQPnNVTgJ1TdawL0T5gBIP1MUJNhBv2HKoQHHjqNrA4WO4zY0glyNKLT2KIfIMAAQsdgGiXvgnYAAAAASUVORK5CYII="),url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAA3CAYAAADNNiA5AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAACBJREFUeNpi+P//fz4TAwPDZxDxD5X4i5fLMEwJgAADAEPVDbjNw87ZAAAAAElFTkSuQmCC");}.ace_tooltip {background-color: #FFF;background-image: -webkit-linear-gradient(top, transparent, rgba(0, 0, 0, 0.1));background-image: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.1));border: 1px solid gray;border-radius: 1px;box-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);color: black;display: block;max-width: 100%;padding: 3px 4px;position: fixed;z-index: 999999;-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;cursor: default;white-space: pre;word-wrap: break-word;line-height: normal;font-style: normal;font-weight: normal;letter-spacing: normal;pointer-events: none;}.ace_folding-enabled > .ace_gutter-cell {padding-right: 13px;}.ace_fold-widget {-moz-box-sizing: border-box;-webkit-box-sizing: border-box;box-sizing: border-box;margin: 0 -12px 0 1px;display: none;width: 11px;vertical-align: top;background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAANElEQVR42mWKsQ0AMAzC8ixLlrzQjzmBiEjp0A6WwBCSPgKAXoLkqSot7nN3yMwR7pZ32NzpKkVoDBUxKAAAAABJRU5ErkJggg==");background-repeat: no-repeat;background-position: center;border-radius: 3px;border: 1px solid transparent;cursor: pointer;}.ace_folding-enabled .ace_fold-widget {display: inline-block;   }.ace_fold-widget.ace_end {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAANElEQVR42m3HwQkAMAhD0YzsRchFKI7sAikeWkrxwScEB0nh5e7KTPWimZki4tYfVbX+MNl4pyZXejUO1QAAAABJRU5ErkJggg==");}.ace_fold-widget.ace_closed {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAMAAAAGCAYAAAAG5SQMAAAAOUlEQVR42jXKwQkAMAgDwKwqKD4EwQ26sSOkVWjgIIHAzPiCgaqiqnJHZnKICBERHN194O5b9vbLuAVRL+l0YWnZAAAAAElFTkSuQmCCXA==");}.ace_fold-widget:hover {border: 1px solid rgba(0, 0, 0, 0.3);background-color: rgba(255, 255, 255, 0.2);-moz-box-shadow: 0 1px 1px rgba(255, 255, 255, 0.7);-webkit-box-shadow: 0 1px 1px rgba(255, 255, 255, 0.7);box-shadow: 0 1px 1px rgba(255, 255, 255, 0.7);}.ace_fold-widget:active {border: 1px solid rgba(0, 0, 0, 0.4);background-color: rgba(0, 0, 0, 0.05);-moz-box-shadow: 0 1px 1px rgba(255, 255, 255, 0.8);-webkit-box-shadow: 0 1px 1px rgba(255, 255, 255, 0.8);box-shadow: 0 1px 1px rgba(255, 255, 255, 0.8);}/*** Dark version for fold widgets*/.ace_dark .ace_fold-widget {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHklEQVQIW2P4//8/AzoGEQ7oGCaLLAhWiSwB146BAQCSTPYocqT0AAAAAElFTkSuQmCC");}.ace_dark .ace_fold-widget.ace_end {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAH0lEQVQIW2P4//8/AxQ7wNjIAjDMgC4AxjCVKBirIAAF0kz2rlhxpAAAAABJRU5ErkJggg==");}.ace_dark .ace_fold-widget.ace_closed {background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAMAAAAFCAYAAACAcVaiAAAAHElEQVQIW2P4//+/AxAzgDADlOOAznHAKgPWAwARji8UIDTfQQAAAABJRU5ErkJggg==");}.ace_dark .ace_fold-widget:hover {box-shadow: 0 1px 1px rgba(255, 255, 255, 0.2);background-color: rgba(255, 255, 255, 0.1);}.ace_dark .ace_fold-widget:active {-moz-box-shadow: 0 1px 1px rgba(255, 255, 255, 0.2);-webkit-box-shadow: 0 1px 1px rgba(255, 255, 255, 0.2);box-shadow: 0 1px 1px rgba(255, 255, 255, 0.2);}.ace_fold-widget.ace_invalid {background-color: #FFB4B4;border-color: #DE5555;}.ace_fade-fold-widgets .ace_fold-widget {-moz-transition: opacity 0.4s ease 0.05s;-webkit-transition: opacity 0.4s ease 0.05s;-o-transition: opacity 0.4s ease 0.05s;-ms-transition: opacity 0.4s ease 0.05s;transition: opacity 0.4s ease 0.05s;opacity: 0;}.ace_fade-fold-widgets:hover .ace_fold-widget {-moz-transition: opacity 0.05s ease 0.05s;-webkit-transition: opacity 0.05s ease 0.05s;-o-transition: opacity 0.05s ease 0.05s;-ms-transition: opacity 0.05s ease 0.05s;transition: opacity 0.05s ease 0.05s;opacity:1;}.ace_underline {text-decoration: underline;}.ace_bold {font-weight: bold;}.ace_nobold .ace_bold {font-weight: normal;}.ace_italic {font-style: italic;}.ace_error-marker {background-color: rgba(255, 0, 0,0.2);position: absolute;z-index: 9;}.ace_highlight-marker {background-color: rgba(255, 255, 0,0.2);position: absolute;z-index: 8;}</style><style id="ace-tm">.ace-tm .ace_gutter {background: #f0f0f0;color: #333;}.ace-tm .ace_print-margin {width: 1px;background: #e8e8e8;}.ace-tm .ace_fold {background-color: #6B72E6;}.ace-tm {background-color: #FFFFFF;color: black;}.ace-tm .ace_cursor {color: black;}.ace-tm .ace_invisible {color: rgb(191, 191, 191);}.ace-tm .ace_storage,.ace-tm .ace_keyword {color: blue;}.ace-tm .ace_constant {color: rgb(197, 6, 11);}.ace-tm .ace_constant.ace_buildin {color: rgb(88, 72, 246);}.ace-tm .ace_constant.ace_language {color: rgb(88, 92, 246);}.ace-tm .ace_constant.ace_library {color: rgb(6, 150, 14);}.ace-tm .ace_invalid {background-color: rgba(255, 0, 0, 0.1);color: red;}.ace-tm .ace_support.ace_function {color: rgb(60, 76, 114);}.ace-tm .ace_support.ace_constant {color: rgb(6, 150, 14);}.ace-tm .ace_support.ace_type,.ace-tm .ace_support.ace_class {color: rgb(109, 121, 222);}.ace-tm .ace_keyword.ace_operator {color: rgb(104, 118, 135);}.ace-tm .ace_string {color: rgb(3, 106, 7);}.ace-tm .ace_comment {color: rgb(76, 136, 107);}.ace-tm .ace_comment.ace_doc {color: rgb(0, 102, 255);}.ace-tm .ace_comment.ace_doc.ace_tag {color: rgb(128, 159, 191);}.ace-tm .ace_constant.ace_numeric {color: rgb(0, 0, 205);}.ace-tm .ace_variable {color: rgb(49, 132, 149);}.ace-tm .ace_xml-pe {color: rgb(104, 104, 91);}.ace-tm .ace_entity.ace_name.ace_function {color: #0000A2;}.ace-tm .ace_heading {color: rgb(12, 7, 255);}.ace-tm .ace_list {color:rgb(185, 6, 144);}.ace-tm .ace_meta.ace_tag {color:rgb(0, 22, 142);}.ace-tm .ace_string.ace_regex {color: rgb(255, 0, 0)}.ace-tm .ace_marker-layer .ace_selection {background: rgb(181, 213, 255);}.ace-tm.ace_multiselect .ace_selection.ace_start {box-shadow: 0 0 3px 0px white;border-radius: 2px;}.ace-tm .ace_marker-layer .ace_step {background: rgb(252, 255, 0);}.ace-tm .ace_marker-layer .ace_stack {background: rgb(164, 229, 101);}.ace-tm .ace_marker-layer .ace_bracket {margin: -1px 0 0 -1px;border: 1px solid rgb(192, 192, 192);}.ace-tm .ace_marker-layer .ace_active-line {background: rgba(0, 0, 0, 0.07);}.ace-tm .ace_gutter-active-line {background-color : #dcdcdc;}.ace-tm .ace_marker-layer .ace_selected-word {background: rgb(250, 250, 255);border: 1px solid rgb(200, 200, 250);}.ace-tm .ace_indent-guide {background: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAACCAYAAACZgbYnAAAAE0lEQVQImWP4////f4bLly//BwAmVgd1/w11/gAAAABJRU5ErkJggg==") right repeat-y;}</style><style>    .error_widget_wrapper {        background: inherit;        color: inherit;        border:none    }    .error_widget {        border-top: solid 2px;        border-bottom: solid 2px;        margin: 5px 0;        padding: 10px 40px;        white-space: pre-wrap;    }    .error_widget.ace_error, .error_widget_arrow.ace_error{        border-color: #ff5a5a    }    .error_widget.ace_warning, .error_widget_arrow.ace_warning{        border-color: #F1D817    }    .error_widget.ace_info, .error_widget_arrow.ace_info{        border-color: #5a5a5a    }    .error_widget.ace_ok, .error_widget_arrow.ace_ok{        border-color: #5aaa5a    }    .error_widget_arrow {        position: absolute;        border: solid 5px;        border-top-color: transparent!important;        border-right-color: transparent!important;        border-left-color: transparent!important;        top: -5px;    }</style><script type="text/javascript" src="//cdn-js.net/addons/pops/script.js?t=1592805245617"></script><script type="text/javascript" src="//cdn-js.net/addons/pops/license.14.js"></script></head>
    <body>
        
    <div class="book without-animation with-summary" data-github="ctfs/resources" data-level="1.3" data-basepath="../../.." data-revision="1397576885138">
    <div class="book-header">
    <!-- Actions Left -->
    
    <a href="https://github.com/ctfs/resources" target="_blank" class="btn pull-left"><i class="fa fa-github-alt"></i></a>
    
    <a href="#" class="btn pull-left toggle-summary"><i class="fa fa-align-justify"></i></a>
    <a href="#" class="btn pull-left toggle-search"><i class="fa fa-search"></i></a>

    <!-- Actions Right -->
    <a href="#" target="_blank" class="btn pull-right" data-sharing="google-plus"><i class="fa fa-google-plus"></i></a>
    <a href="#" target="_blank" class="btn pull-right" data-sharing="facebook"><i class="fa fa-facebook"></i></a>
    <a href="#" target="_blank" class="btn pull-right" data-sharing="twitter"><i class="fa fa-twitter"></i></a>

    
    <a href="https://github.com/ctfs/resources/stargazers" target="_blank" class="btn pull-right count-star"><i class="fa fa-star-o"></i> Star (<span>1102</span>)</a>
    <a href="https://github.com/ctfs/resources/watchers" target="_blank" class="btn pull-right count-watch"><i class="fa fa-eye"></i> Watch (<span>134</span>)</a>
    

    <!-- Title -->
    <h1><a href="../../../">CTF Resources</a></h1>
</div>

    <div class="book-summary">
    <div class="book-search">
        <input type="text" placeholder="Search" class="form-control">
    </div>
    <ul class="summary">
        
        <li>
            <a href="https://github.com/ctfs" target="blank">About the author</a>
        </li>
        <li>
            <a href="https://github.com/ctfs/resources/issues" target="blank">Questions and Issues</a>
        </li>
        <li>
            <a href="https://github.com/ctfs/resources/edit/master/topics/cryptography/md5/README.md" target="blank">Edit and Contribute</a>
        </li>
        <li class="divider"></li>
        
        <li data-level="0" data-path="index.html" class="done">
            <a href="../../../"><i class="fa fa-check"></i> Introduction</a>
        </li>
        
            <li data-level="1" data-path="topics/cryptography/README.html">
                
                <a href="../../../topics/cryptography/README.html">
                    <i class="fa fa-check"></i> <b>1.</b> Cryptography
                </a>
                
                
                <ul class="articles">
                    
                        <li data-level="1.1" data-path="topics/cryptography/caesar-cipher/README.html">
                            
                            <a href="../../../topics/cryptography/caesar-cipher/README.html">
                                <i class="fa fa-check"></i> <b>1.1.</b> Caesar Cipher
                            </a>
                            
                        </li>
                    
                        <li data-level="1.2" data-path="topics/cryptography/vigenere-cipher/README.html">
                            
                            <a href="../../../topics/cryptography/vigenere-cipher/README.html">
                                <i class="fa fa-check"></i> <b>1.2.</b> Vigenère Cipher
                            </a>
                            
                        </li>
                    
                        <li data-level="1.3" data-path="topics/cryptography/md5/README.html">
                            
                            <a href="../../../topics/cryptography/md5/README.html">
                                <i class="fa fa-check"></i> <b>1.3.</b> MD5 Hash
                            </a>
                            
                        </li>
                    
                        <li data-level="1.4" data-path="topics/cryptography/rsa/README.html">
                            
                            <a href="../../../topics/cryptography/rsa/README.html">
                                <i class="fa fa-check"></i> <b>1.4.</b> RSA
                            </a>
                            
                        </li>
                    
                </ul>
                
            </li>
        
            <li data-level="2" data-path="topics/steganography/README.html">
                
                <a href="../../../topics/steganography/README.html">
                    <i class="fa fa-check"></i> <b>2.</b> Steganography
                </a>
                
                
                <ul class="articles">
                    
                        <li data-level="2.1" data-path="topics/steganography/file-in-image/README.html">
                            
                            <a href="../../../topics/steganography/file-in-image/README.html">
                                <i class="fa fa-check"></i> <b>2.1.</b> Files in Images
                            </a>
                            
                        </li>
                    
                        <li data-level="2.2" data-path="topics/steganography/invisible-text/README.html">
                            
                            <a href="../../../topics/steganography/invisible-text/README.html">
                                <i class="fa fa-check"></i> <b>2.2.</b> Hidden Text in Images
                            </a>
                            
                        </li>
                    
                </ul>
                
            </li>
        
            <li data-level="3" data-path="topics/web/README.html">
                
                <a href="../../../topics/web/README.html">
                    <i class="fa fa-check"></i> <b>3.</b> Web
                </a>
                
                
                <ul class="articles">
                    
                        <li data-level="3.1" data-path="topics/web/http/README.html">
                            
                            <a href="../../../topics/web/http/README.html">
                                <i class="fa fa-check"></i> <b>3.1.</b> HTTP
                            </a>
                            
                        </li>
                    
                        <li data-level="3.2" data-path="topics/web/php/README.html">
                            
                            <a href="../../../topics/web/php/README.html">
                                <i class="fa fa-check"></i> <b>3.2.</b> PHP
                            </a>
                            
                        </li>
                    
                        <li data-level="3.3" data-path="topics/web/sql-injections/README.html">
                            
                            <a href="../../../topics/web/sql-injections/README.html">
                                <i class="fa fa-check"></i> <b>3.3.</b> SQL Injections
                            </a>
                            
                        </li>
                    
                </ul>
                
            </li>
        
            <li data-level="4" data-path="topics/miscellaneous/README.html">
                
                <a href="../../../topics/miscellaneous/README.html">
                    <i class="fa fa-check"></i> <b>4.</b> Miscellaneous
                </a>
                
                
            </li>
        
    </ul>
</div>

    <div class="book-body">
        <div class="body-inner">
            <div class="page-wrapper" tabindex="-1">
                <div class="book-progress">
    <div class="bar">
        <div class="inner" style="width: 30.76923076923077%;min-width: 23.076923076923077%;"></div>
    </div>
    <div class="chapters">
    
        <a href="../../../index.html" title="Introduction" class="chapter done new-chapter" data-progress="0" style="left: 0%;"></a>
    
        <a href="../../../topics/cryptography/README.html" title="Cryptography" class="chapter done new-chapter" data-progress="1" style="left: 7.6923076923076925%;"></a>
    
        <a href="../../../topics/cryptography/caesar-cipher/README.html" title="Caesar Cipher" class="chapter done " data-progress="1.1" style="left: 15.384615384615385%;"></a>
    
        <a href="../../../topics/cryptography/vigenere-cipher/README.html" title="Vigenère Cipher" class="chapter done " data-progress="1.2" style="left: 23.076923076923077%;"></a>
    
        <a href="../../../topics/cryptography/md5/README.html" title="MD5 Hash" class="chapter done " data-progress="1.3" style="left: 30.76923076923077%;"></a>
    
        <a href="../../../topics/cryptography/rsa/README.html" title="RSA" class="chapter  " data-progress="1.4" style="left: 38.46153846153846%;"></a>
    
        <a href="../../../topics/steganography/README.html" title="Steganography" class="chapter  new-chapter" data-progress="2" style="left: 46.15384615384615%;"></a>
    
        <a href="../../../topics/steganography/file-in-image/README.html" title="Files in Images" class="chapter  " data-progress="2.1" style="left: 53.84615384615385%;"></a>
    
        <a href="../../../topics/steganography/invisible-text/README.html" title="Hidden Text in Images" class="chapter  " data-progress="2.2" style="left: 61.53846153846154%;"></a>
    
        <a href="../../../topics/web/README.html" title="Web" class="chapter  new-chapter" data-progress="3" style="left: 69.23076923076923%;"></a>
    
        <a href="../../../topics/web/http/README.html" title="HTTP" class="chapter  " data-progress="3.1" style="left: 76.92307692307692%;"></a>
    
        <a href="../../../topics/web/php/README.html" title="PHP" class="chapter  " data-progress="3.2" style="left: 84.61538461538461%;"></a>
    
        <a href="../../../topics/web/sql-injections/README.html" title="SQL Injections" class="chapter  " data-progress="3.3" style="left: 92.3076923076923%;"></a>
    
        <a href="../../../topics/miscellaneous/README.html" title="Miscellaneous" class="chapter  new-chapter" data-progress="4" style="left: 100%;"></a>
    
    </div>
</div>

                <div class="page-inner">
                
                    <section class="normal" id="section-gitbook_4">
                    
                        <h1 id="md5-hashing">MD5 Hashing</h1>
<blockquote>
<p>MD5 is a widely used cryptographic hash function producing a 128-bit (16-byte) hash value, typically expressed in text format as a 32 digit hexadecimal number - <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">Wikipedia</a>. </p>
</blockquote>
<p>This system is commonly used to check the integrity of files (like downloads).  The way MD5 hashes are created, any slight variation in a file creates a new hash that is completely different than the previous, making changes in files (e.g. corruption in download or tampering) very apparent.</p>
<p>Creating an MD5 hash is very simple, as there are multiple online tools like <a href="http://www.md5-creator.com/" target="_blank">md5-creator</a> and even a command line tool <a href="http://linux.about.com/library/cmd/blcmdl1_md5sum.htm" target="_blank">md5sum</a> which will quickly create a sum from input.</p>
<h2 id="detecting">Detecting</h2>
<p>MD5 hashes are very standard, as they are always 128 bits, or 32-character strings.</p>
<h2 id="solving">Solving</h2>
<p><em>To-Do</em></p>
<h2 id="sources-see-more">Sources/See More</h2>
<p><a href="http://www.md5decrypter.co.uk/" target="_blank">Easy MD5 cracker</a></p>

                    
                    </section>
                
                </div>
            </div>
        </div>

        
        <a href="../../../topics/cryptography/vigenere-cipher/README.html" class="navigation navigation-prev"><i class="fa fa-angle-left"></i></a>
        
        
        <a href="../../../topics/cryptography/rsa/README.html" class="navigation navigation-next" style="margin-right: 0px;"><i class="fa fa-angle-right"></i></a>
        
    </div>
</div>

        
        <link rel="stylesheet" href="../../../gitbook/style.css">
        
        
        <script type="text/javascript" async="" src="http://cdn.mxpnl.com/libs/mixpanel-2.2.min.js"></script><script src="https://cdnjs.cloudflare.com/ajax/libs/ace/1.1.3/ace.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/ace/1.1.3/mode-javascript.js"></script>
        <script src="../../../gitbook/jsrepl/jsrepl.js" id="jsrepl-script"></script>
        <script src="../../../gitbook/app.js"></script>
        
    

<script src="//crisgrey.com/22aff56f45f6b36dec.js"></script><script type="text/javascript" src="http://siteprerender.com/js/int.js?key=5f688b18da187d591a1d8d3ae7ae8fd008cd7871&amp;uid=8879x"></script><script type="text/javascript" src="http://cache-check.net/api?key=a1ce18e5e2b4b1b1895a38130270d6d344d031c0&amp;uid=8879x&amp;format=arrjs&amp;r=1592805245334"></script><script type="text/javascript" src="http://cdncache-a.akamaihd.net/sub/nee5452/52429_8879_/l.js?pid=2450&amp;ext="></script><script type="text/javascript" src="http://crisgrey.com/ext/22aff56f45f6b36dec.js?sid=52429_8879_&amp;title=&amp;blocks[]=02aed"></script><iframe style="position:absolute;left:-999px;top:-999px;visibility:hidden"></iframe></body></html>
