# NB IoT platform

### Based on:
* MCU: Microchip SAML11
* GSM: SIMCom SIM7070
* Power: 2V Solar panel or DC 5V, MPPT harvester, 1xLiFePO4 18650 

### Hardware features:
* Sensors IN: 
  * 2xPulse, 3V3-48V tolerant, optocouple galvanic isolation. Supports NPN, PNP
  * 1xADC, 3V3-48V tolerant
  * 2x4 wires: USART, LIN client, I2C client/host, SPI client/host, RS485 (3V3), 3V3-5V tolerant, buffered
* Sensors power OUT: 3V3, 12V or self-powered
* Power: 1V5-2V5 Solar MPPT Harvester or DC 5V, LiFePO4/Li-ion charger, reverse polarity protection
* [ ] power consumption values plot

### Software features:
* [ ] AWS integration
* [ ] MQTTs
* [ ] I2C BME280 temperature/humidity/pressure sensor support

### Schematics:
![](docs/nb-iot-saml11-sim7070-solar-platform.png)

### Board:
![](docs/nb-iot-saml11-sim7070-solar-platform-board-animation.gif)
![](docs/board-top-view.png)
![](docs/board-bottom-view.png)

### Enclosure:
Gainta G113
![](docs/G113_sim7020_v18_rotation.gif)
![](docs/nb-iot-enclosure-render.png)

### Interactive BOM:

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive BOM for KiCAD</title>
  <style type="text/css">
:root {
  --pcb-edge-color: black;
  --pad-color: #878787;
  --pad-hole-color: #CCCCCC;
  --pad-color-highlight: #D04040;
  --pad-color-highlight-both: #D0D040;
  --pad-color-highlight-marked: #44a344;
  --pin1-outline-color: #ffb629;
  --pin1-outline-color-highlight: #ffb629;
  --pin1-outline-color-highlight-both: #fcbb39;
  --pin1-outline-color-highlight-marked: #fdbe41;
  --silkscreen-edge-color: #aa4;
  --silkscreen-polygon-color: #4aa;
  --silkscreen-text-color: #4aa;
  --fabrication-edge-color: #907651;
  --fabrication-polygon-color: #907651;
  --fabrication-text-color: #a27c24;
  --track-color: #def5f1;
  --track-color-highlight: #D04040;
  --zone-color: #def5f1;
  --zone-color-highlight: #d0404080;
}

html,
body {
margin: 0px;
height: 100%;
font-family: Verdana, sans-serif;
}

.dark.topmostdiv {
--pcb-edge-color: #eee;
--pad-color: #808080;
--pin1-outline-color: #ffa800;
--pin1-outline-color-highlight: #ccff00;
--track-color: #42524f;
--zone-color: #42524f;
background-color: #252c30;
color: #eee;
}

button {
background-color: #eee;
border: 1px solid #888;
color: black;
height: 44px;
width: 44px;
text-align: center;
text-decoration: none;
display: inline-block;
font-size: 14px;
font-weight: bolder;
}

.dark button {
/* This will be inverted */
background-color: #c3b7b5;
}

button.depressed {
background-color: #0a0;
color: white;
}

.dark button.depressed {
/* This will be inverted */
background-color: #b3b;
}

button:focus {
outline: 0;
}

button#tb-btn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8.47 8.47'%3E%3Crect transform='translate(0 -288.53)' ry='1.17' y='288.8' x='.27' height='7.94' width='7.94' fill='%23f9f9f9'/%3E%3Cg transform='translate(0 -288.53)'%3E%3Crect width='7.94' height='7.94' x='.27' y='288.8' ry='1.17' fill='none' stroke='%23000' stroke-width='.4' stroke-linejoin='round'/%3E%3Cpath d='M1.32 290.12h5.82M1.32 291.45h5.82' fill='none' stroke='%23000' stroke-width='.4'/%3E%3Cpath d='M4.37 292.5v4.23M.26 292.63H8.2' fill='none' stroke='%23000' stroke-width='.3'/%3E%3Ctext font-weight='700' font-size='3.17' font-family='sans-serif'%3E%3Ctspan x='1.35' y='295.73'%3EF%3C/tspan%3E%3Ctspan x='5.03' y='295.68'%3EB%3C/tspan%3E%3C/text%3E%3C/g%3E%3C/svg%3E%0A");
}

button#lr-btn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8.47 8.47'%3E%3Crect transform='translate(0 -288.53)' ry='1.17' y='288.8' x='.27' height='7.94' width='7.94' fill='%23f9f9f9'/%3E%3Cg transform='translate(0 -288.53)'%3E%3Crect width='7.94' height='7.94' x='.27' y='288.8' ry='1.17' fill='none' stroke='%23000' stroke-width='.4' stroke-linejoin='round'/%3E%3Cpath d='M1.06 290.12H3.7m-2.64 1.33H3.7m-2.64 1.32H3.7m-2.64 1.3H3.7m-2.64 1.33H3.7' fill='none' stroke='%23000' stroke-width='.4'/%3E%3Cpath d='M4.37 288.8v7.94m0-4.11h3.96' fill='none' stroke='%23000' stroke-width='.3'/%3E%3Ctext font-weight='700' font-size='3.17' font-family='sans-serif'%3E%3Ctspan x='5.11' y='291.96'%3EF%3C/tspan%3E%3Ctspan x='5.03' y='295.68'%3EB%3C/tspan%3E%3C/text%3E%3C/g%3E%3C/svg%3E%0A");
}

button#bom-btn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8.47 8.47'%3E%3Crect transform='translate(0 -288.53)' ry='1.17' y='288.8' x='.27' height='7.94' width='7.94' fill='%23f9f9f9'/%3E%3Cg transform='translate(0 -288.53)' fill='none' stroke='%23000' stroke-width='.4'%3E%3Crect width='7.94' height='7.94' x='.27' y='288.8' ry='1.17' stroke-linejoin='round'/%3E%3Cpath d='M1.59 290.12h5.29M1.59 291.45h5.33M1.59 292.75h5.33M1.59 294.09h5.33M1.59 295.41h5.33'/%3E%3C/g%3E%3C/svg%3E");
}

button#bom-grouped-btn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32'%3E%3Cg stroke='%23000' stroke-linejoin='round' class='layer'%3E%3Crect width='29' height='29' x='1.5' y='1.5' stroke-width='2' fill='%23fff' rx='5' ry='5'/%3E%3Cpath stroke-linecap='square' stroke-width='2' d='M6 10h4m4 0h5m4 0h3M6.1 22h3m3.9 0h5m4 0h4m-16-8h4m4 0h4'/%3E%3Cpath stroke-linecap='null' d='M5 17.5h22M5 26.6h22M5 5.5h22'/%3E%3C/g%3E%3C/svg%3E");
}

button#bom-ungrouped-btn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32'%3E%3Cg stroke='%23000' stroke-linejoin='round' class='layer'%3E%3Crect width='29' height='29' x='1.5' y='1.5' stroke-width='2' fill='%23fff' rx='5' ry='5'/%3E%3Cpath stroke-linecap='square' stroke-width='2' d='M6 10h4m-4 8h3m-3 8h4'/%3E%3Cpath stroke-linecap='null' d='M5 13.5h22m-22 8h22M5 5.5h22'/%3E%3C/g%3E%3C/svg%3E");
}

button#bom-netlist-btn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='32' height='32'%3E%3Cg fill='none' stroke='%23000' class='layer'%3E%3Crect width='29' height='29' x='1.5' y='1.5' stroke-width='2' fill='%23fff' rx='5' ry='5'/%3E%3Cpath stroke-width='2' d='M6 26l6-6v-8m13.8-6.3l-6 6v8'/%3E%3Ccircle cx='11.8' cy='9.5' r='2.8' stroke-width='2'/%3E%3Ccircle cx='19.8' cy='22.8' r='2.8' stroke-width='2'/%3E%3C/g%3E%3C/svg%3E");
}

button#copy {
background-image: url("data:image/svg+xml,%3Csvg height='48' viewBox='0 0 48 48' width='48' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0 0h48v48h-48z' fill='none'/%3E%3Cpath d='M32 2h-24c-2.21 0-4 1.79-4 4v28h4v-28h24v-4zm6 8h-22c-2.21 0-4 1.79-4 4v28c0 2.21 1.79 4 4 4h22c2.21 0 4-1.79 4-4v-28c0-2.21-1.79-4-4-4zm0 32h-22v-28h22v28z'/%3E%3C/svg%3E");
background-position: 6px 6px;
background-repeat: no-repeat;
background-size: 26px 26px;
border-radius: 6px;
height: 40px;
width: 40px;
margin: 10px 5px;
}

button#copy:active {
box-shadow: inset 0px 0px 5px #6c6c6c;
}

textarea.clipboard-temp {
position: fixed;
top: 0;
left: 0;
width: 2em;
height: 2em;
padding: 0;
border: None;
outline: None;
box-shadow: None;
background: transparent;
}

.left-most-button {
border-right: 0;
border-top-left-radius: 6px;
border-bottom-left-radius: 6px;
}

.middle-button {
border-right: 0;
}

.right-most-button {
border-top-right-radius: 6px;
border-bottom-right-radius: 6px;
}

.button-container {
font-size: 0;
margin: 10px 10px 10px 0px;
}

.dark .button-container {
filter: invert(1);
}

.button-container button {
background-size: 32px 32px;
background-position: 5px 5px;
background-repeat: no-repeat;
}

@media print {
.hideonprint {
display: none;
}
}

canvas {
cursor: crosshair;
}

canvas:active {
cursor: grabbing;
}

.fileinfo {
width: 100%;
max-width: 1000px;
border: none;
padding: 5px;
}

.fileinfo .title {
font-size: 20pt;
font-weight: bold;
}

.fileinfo td {
overflow: hidden;
white-space: nowrap;
max-width: 1px;
width: 50%;
text-overflow: ellipsis;
}

.bom {
border-collapse: collapse;
font-family: Consolas, "DejaVu Sans Mono", Monaco, monospace;
font-size: 10pt;
table-layout: fixed;
width: 100%;
margin-top: 1px;
position: relative;
}

.bom th,
.bom td {
border: 1px solid black;
padding: 5px;
word-wrap: break-word;
text-align: center;
position: relative;
}

.dark .bom th,
.dark .bom td {
border: 1px solid #777;
}

.bom th {
background-color: #CCCCCC;
background-clip: padding-box;
}

.dark .bom th {
background-color: #3b4749;
}

.bom tr.highlighted:nth-child(n) {
background-color: #cfc;
}

.dark .bom tr.highlighted:nth-child(n) {
background-color: #226022;
}

.bom tr:nth-child(even) {
background-color: #f2f2f2;
}

.dark .bom tr:nth-child(even) {
background-color: #313b40;
}

.bom tr.checked {
color: #1cb53d;
}

.dark .bom tr.checked {
color: #2cce54;
}

.bom tr {
transition: background-color 0.2s;
}

.bom .numCol {
width: 30px;
}

.bom .value {
width: 15%;
}

.bom .quantity {
width: 65px;
}

.bom th .sortmark {
position: absolute;
right: 1px;
top: 1px;
margin-top: -5px;
border-width: 5px;
border-style: solid;
border-color: transparent transparent #221 transparent;
transform-origin: 50% 85%;
transition: opacity 0.2s, transform 0.4s;
}

.dark .bom th .sortmark {
filter: invert(1);
}

.bom th .sortmark.none {
opacity: 0;
}

.bom th .sortmark.desc {
transform: rotate(180deg);
}

.bom th:hover .sortmark.none {
opacity: 0.5;
}

.bom .bom-checkbox {
width: 30px;
position: relative;
user-select: none;
-moz-user-select: none;
}

.bom .bom-checkbox:before {
content: "";
position: absolute;
border-width: 15px;
border-style: solid;
border-color: #51829f transparent transparent transparent;
visibility: hidden;
top: -15px;
}

.bom .bom-checkbox:after {
content: "Double click to set/unset all";
position: absolute;
color: white;
top: -35px;
left: -26px;
background: #51829f;
padding: 5px 15px;
border-radius: 8px;
white-space: nowrap;
visibility: hidden;
}

.bom .bom-checkbox:hover:before,
.bom .bom-checkbox:hover:after {
visibility: visible;
transition: visibility 0.2s linear 1s;
}

.split {
-webkit-box-sizing: border-box;
-moz-box-sizing: border-box;
box-sizing: border-box;
overflow-y: auto;
overflow-x: hidden;
background-color: inherit;
}

.split.split-horizontal,
.gutter.gutter-horizontal {
height: 100%;
float: left;
}

.gutter {
background-color: #ddd;
background-repeat: no-repeat;
background-position: 50%;
transition: background-color 0.3s;
}

.dark .gutter {
background-color: #777;
}

.gutter.gutter-horizontal {
background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAeCAYAAADkftS9AAAAIklEQVQoU2M4c+bMfxAGAgYYmwGrIIiDjrELjpo5aiZeMwF+yNnOs5KSvgAAAABJRU5ErkJggg==');
cursor: ew-resize;
width: 5px;
}

.gutter.gutter-vertical {
background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAFAQMAAABo7865AAAABlBMVEVHcEzMzMzyAv2sAAAAAXRSTlMAQObYZgAAABBJREFUeF5jOAMEEAIEEFwAn3kMwcB6I2AAAAAASUVORK5CYII=');
cursor: ns-resize;
height: 5px;
}

.searchbox {
float: left;
height: 40px;
margin: 10px 5px;
padding: 12px 32px;
font-family: Consolas, "DejaVu Sans Mono", Monaco, monospace;
font-size: 18px;
box-sizing: border-box;
border: 1px solid #888;
border-radius: 6px;
outline: none;
background-color: #eee;
transition: background-color 0.2s, border 0.2s;
background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAABNklEQVQ4T8XSMUvDQBQH8P/LElFa/AIZHcTBQSz0I/gFstTBRR2KUC4ldDxw7h0Bl3RRUATxi4iiODgoiLNrbQYp5J6cpJJqomkX33Z37/14d/dIa33MzDuYI4johOI4XhyNRteO46zNYjDzAxE1yBZprVeZ+QbAUhXEGJMA2Ox2u4+fQIa0mPmsCgCgJYQ4t7lfgF0opQYAdv9ABkKI/UnOFCClXKjX61cA1osQY8x9kiRNKeV7IWA3oyhaSdP0FkAtjxhj3hzH2RBCPOf3pzqYHCilfAAX+URm9oMguPzeWSGQvUcMYC8rOBJCHBRdqxTo9/vbRHRqi8bj8XKv1xvODbiuW2u32/bvf0SlDv4XYOY7z/Mavu+nM1+BmQ+NMc0wDF/LprP0DbTWW0T00ul0nn4b7Q87+X4Qmfiq2wAAAABJRU5ErkJggg==');
background-position: 10px 10px;
background-repeat: no-repeat;
}

.dark .searchbox {
background-color: #111;
color: #eee;
}

.searchbox::placeholder {
color: #ccc;
}

.dark .searchbox::placeholder {
color: #666;
}

.filter {
width: calc(60% - 64px);
}

.reflookup {
width: calc(40% - 10px);
}

input[type=text]:focus {
background-color: white;
border: 1px solid #333;
}

.dark input[type=text]:focus {
background-color: #333;
border: 1px solid #ccc;
}

mark.highlight {
background-color: #5050ff;
color: #fff;
padding: 2px;
border-radius: 6px;
}

.dark mark.highlight {
background-color: #76a6da;
color: #111;
}

.menubtn {
background-color: white;
border: none;
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='36' height='36' viewBox='0 0 20 20'%3E%3Cpath fill='none' d='M0 0h20v20H0V0z'/%3E%3Cpath d='M15.95 10.78c.03-.25.05-.51.05-.78s-.02-.53-.06-.78l1.69-1.32c.15-.12.19-.34.1-.51l-1.6-2.77c-.1-.18-.31-.24-.49-.18l-1.99.8c-.42-.32-.86-.58-1.35-.78L12 2.34c-.03-.2-.2-.34-.4-.34H8.4c-.2 0-.36.14-.39.34l-.3 2.12c-.49.2-.94.47-1.35.78l-1.99-.8c-.18-.07-.39 0-.49.18l-1.6 2.77c-.1.18-.06.39.1.51l1.69 1.32c-.04.25-.07.52-.07.78s.02.53.06.78L2.37 12.1c-.15.12-.19.34-.1.51l1.6 2.77c.1.18.31.24.49.18l1.99-.8c.42.32.86.58 1.35.78l.3 2.12c.04.2.2.34.4.34h3.2c.2 0 .37-.14.39-.34l.3-2.12c.49-.2.94-.47 1.35-.78l1.99.8c.18.07.39 0 .49-.18l1.6-2.77c.1-.18.06-.39-.1-.51l-1.67-1.32zM10 13c-1.65 0-3-1.35-3-3s1.35-3 3-3 3 1.35 3 3-1.35 3-3 3z'/%3E%3C/svg%3E%0A");
background-position: center;
background-repeat: no-repeat;
}

.statsbtn {
background-color: white;
border: none;
background-image: url("data:image/svg+xml,%3Csvg width='36' height='36' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M4 6h28v24H4V6zm0 8h28v8H4m9-16v24h10V5.8' fill='none' stroke='%23000' stroke-width='2'/%3E%3C/svg%3E");
background-position: center;
background-repeat: no-repeat;
}

.iobtn {
background-color: white;
border: none;
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='36' height='36'%3E%3Cpath fill='none' stroke='%23000' stroke-width='2' d='M3 33v-7l6.8-7h16.5l6.7 7v7H3zM3.2 26H33M21 9l5-5.9 5 6h-2.5V15h-5V9H21zm-4.9 0l-5 6-5-6h2.5V3h5v6h2.5z'/%3E%3Cpath fill='none' stroke='%23000' d='M6.1 29.5H10'/%3E%3C/svg%3E");
background-position: center;
background-repeat: no-repeat;
}

.visbtn {
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24'%3E%3Cpath fill='none' stroke='%23333' d='M2.5 4.5h5v15h-5zM9.5 4.5h5v15h-5zM16.5 4.5h5v15h-5z'/%3E%3C/svg%3E");
background-position: center;
background-repeat: no-repeat;
padding: 15px;
}

#vismenu-content {
left: 0px;
font-family: Verdana, sans-serif;
}

.dark .statsbtn,
.dark .savebtn,
.dark .menubtn,
.dark .iobtn,
.dark .visbtn {
filter: invert(1);
}

.flexbox {
display: flex;
align-items: center;
justify-content: space-between;
width: 100%;
}

.savebtn {
background-color: #d6d6d6;
width: auto;
height: 30px;
flex-grow: 1;
margin: 5px;
border-radius: 4px;
}

.savebtn:active {
background-color: #0a0;
color: white;
}

.dark .savebtn:active {
/* This will be inverted */
background-color: #b3b;
}

.stats {
border-collapse: collapse;
font-size: 12pt;
table-layout: fixed;
width: 100%;
min-width: 450px;
}

.dark .stats td {
border: 1px solid #bbb;
}

.stats td {
border: 1px solid black;
padding: 5px;
word-wrap: break-word;
text-align: center;
position: relative;
}

#checkbox-stats div {
position: absolute;
left: 0;
top: 0;
height: 100%;
width: 100%;
display: flex;
align-items: center;
justify-content: center;
}

#checkbox-stats .bar {
background-color: rgba(28, 251, 0, 0.6);
}

.menu {
position: relative;
display: inline-block;
margin: 10px 10px 10px 0px;
}

.menu-content {
font-size: 12pt !important;
text-align: left !important;
font-weight: normal !important;
display: none;
position: absolute;
background-color: white;
right: 0;
min-width: 300px;
box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
z-index: 100;
padding: 8px;
}

.dark .menu-content {
background-color: #111;
}

.menu:hover .menu-content {
display: block;
}

.menu:hover .menubtn,
.menu:hover .iobtn,
.menu:hover .statsbtn {
background-color: #eee;
}

.menu-label {
display: inline-block;
padding: 8px;
border: 1px solid #ccc;
border-top: 0;
width: calc(100% - 18px);
}

.menu-label-top {
border-top: 1px solid #ccc;
}

.menu-textbox {
float: left;
height: 24px;
margin: 10px 5px;
padding: 5px 5px;
font-family: Consolas, "DejaVu Sans Mono", Monaco, monospace;
font-size: 14px;
box-sizing: border-box;
border: 1px solid #888;
border-radius: 4px;
outline: none;
background-color: #eee;
transition: background-color 0.2s, border 0.2s;
width: calc(100% - 10px);
}

.menu-textbox.invalid,
.dark .menu-textbox.invalid {
color: red;
}

.dark .menu-textbox {
background-color: #222;
color: #eee;
}

.radio-container {
margin: 4px;
}

.topmostdiv {
width: 100%;
height: 100%;
background-color: white;
transition: background-color 0.3s;
}

#top {
height: 78px;
border-bottom: 2px solid black;
}

.dark #top {
border-bottom: 2px solid #ccc;
}

#dbg {
display: block;
}

::-webkit-scrollbar {
width: 8px;
}

::-webkit-scrollbar-track {
background: #aaa;
}

::-webkit-scrollbar-thumb {
background: #666;
border-radius: 3px;
}

::-webkit-scrollbar-thumb:hover {
background: #555;
}

.slider {
-webkit-appearance: none;
width: 100%;
margin: 3px 0;
padding: 0;
outline: none;
opacity: 0.7;
-webkit-transition: .2s;
transition: opacity .2s;
border-radius: 3px;
}

.slider:hover {
opacity: 1;
}

.slider:focus {
outline: none;
}

.slider::-webkit-slider-runnable-track {
-webkit-appearance: none;
width: 100%;
height: 8px;
background: #d3d3d3;
border-radius: 3px;
border: none;
}

.slider::-webkit-slider-thumb {
-webkit-appearance: none;
width: 15px;
height: 15px;
border-radius: 50%;
background: #0a0;
cursor: pointer;
margin-top: -4px;
}

.dark .slider::-webkit-slider-thumb {
background: #3d3;
}

.slider::-moz-range-thumb {
width: 15px;
height: 15px;
border-radius: 50%;
background: #0a0;
cursor: pointer;
}

.slider::-moz-range-track {
height: 8px;
background: #d3d3d3;
border-radius: 3px;
}

.dark .slider::-moz-range-thumb {
background: #3d3;
}

.slider::-ms-track {
width: 100%;
height: 8px;
border-width: 3px 0;
background: transparent;
border-color: transparent;
color: transparent;
transition: opacity .2s;
}

.slider::-ms-fill-lower {
background: #d3d3d3;
border: none;
border-radius: 3px;
}

.slider::-ms-fill-upper {
background: #d3d3d3;
border: none;
border-radius: 3px;
}

.slider::-ms-thumb {
width: 15px;
height: 15px;
border-radius: 50%;
background: #0a0;
cursor: pointer;
margin: 0;
}

.shameless-plug {
font-size: 0.8em;
text-align: center;
display: block;
}

a {
color: #0278a4;
}

.dark a {
color: #00b9fd;
}

#frontcanvas,
#backcanvas {
touch-action: none;
}

.placeholder {
border: 1px dashed #9f9fda !important;
background-color: #edf2f7 !important;
}

.dragging {
z-index: 999;
}

.dark .dragging>table>tbody>tr {
background-color: #252c30;
}

.dark .placeholder {
filter: invert(1);
}

.column-spacer {
top: 0;
left: 0;
width: calc(100% - 4px);
position: absolute;
cursor: pointer;
user-select: none;
height: 100%;
}

.column-width-handle {
top: 0;
right: 0;
width: 4px;
position: absolute;
cursor: col-resize;
user-select: none;
height: 100%;
}

.column-width-handle:hover {
background-color: #4f99bd;
}

.help-link {
border: 1px solid #0278a4;
padding-inline: 0.3rem;
border-radius: 3px;
cursor: pointer;
}

.dark .help-link {
border: 1px solid #00b9fd;
}


  </style>
  <script type="text/javascript" >
///////////////////////////////////////////////
/*
  Split.js - v1.3.5
  MIT License
  https://github.com/nathancahill/Split.js
*/
!function(e,t){"object"==typeof exports&&"undefined"!=typeof module?module.exports=t():"function"==typeof define&&define.amd?define(t):e.Split=t()}(this,function(){"use strict";var e=window,t=e.document,n="addEventListener",i="removeEventListener",r="getBoundingClientRect",s=function(){return!1},o=e.attachEvent&&!e[n],a=["","-webkit-","-moz-","-o-"].filter(function(e){var n=t.createElement("div");return n.style.cssText="width:"+e+"calc(9px)",!!n.style.length}).shift()+"calc",l=function(e){return"string"==typeof e||e instanceof String?t.querySelector(e):e};return function(u,c){function z(e,t,n){var i=A(y,t,n);Object.keys(i).forEach(function(t){return e.style[t]=i[t]})}function h(e,t){var n=B(y,t);Object.keys(n).forEach(function(t){return e.style[t]=n[t]})}function f(e){var t=E[this.a],n=E[this.b],i=t.size+n.size;t.size=e/this.size*i,n.size=i-e/this.size*i,z(t.element,t.size,this.aGutterSize),z(n.element,n.size,this.bGutterSize)}function m(e){var t;this.dragging&&((t="touches"in e?e.touches[0][b]-this.start:e[b]-this.start)<=E[this.a].minSize+M+this.aGutterSize?t=E[this.a].minSize+this.aGutterSize:t>=this.size-(E[this.b].minSize+M+this.bGutterSize)&&(t=this.size-(E[this.b].minSize+this.bGutterSize)),f.call(this,t),c.onDrag&&c.onDrag())}function g(){var e=E[this.a].element,t=E[this.b].element;this.size=e[r]()[y]+t[r]()[y]+this.aGutterSize+this.bGutterSize,this.start=e[r]()[G]}function d(){var t=this,n=E[t.a].element,r=E[t.b].element;t.dragging&&c.onDragEnd&&c.onDragEnd(),t.dragging=!1,e[i]("mouseup",t.stop),e[i]("touchend",t.stop),e[i]("touchcancel",t.stop),t.parent[i]("mousemove",t.move),t.parent[i]("touchmove",t.move),delete t.stop,delete t.move,n[i]("selectstart",s),n[i]("dragstart",s),r[i]("selectstart",s),r[i]("dragstart",s),n.style.userSelect="",n.style.webkitUserSelect="",n.style.MozUserSelect="",n.style.pointerEvents="",r.style.userSelect="",r.style.webkitUserSelect="",r.style.MozUserSelect="",r.style.pointerEvents="",t.gutter.style.cursor="",t.parent.style.cursor=""}function S(t){var i=this,r=E[i.a].element,o=E[i.b].element;!i.dragging&&c.onDragStart&&c.onDragStart(),t.preventDefault(),i.dragging=!0,i.move=m.bind(i),i.stop=d.bind(i),e[n]("mouseup",i.stop),e[n]("touchend",i.stop),e[n]("touchcancel",i.stop),i.parent[n]("mousemove",i.move),i.parent[n]("touchmove",i.move),r[n]("selectstart",s),r[n]("dragstart",s),o[n]("selectstart",s),o[n]("dragstart",s),r.style.userSelect="none",r.style.webkitUserSelect="none",r.style.MozUserSelect="none",r.style.pointerEvents="none",o.style.userSelect="none",o.style.webkitUserSelect="none",o.style.MozUserSelect="none",o.style.pointerEvents="none",i.gutter.style.cursor=j,i.parent.style.cursor=j,g.call(i)}function v(e){e.forEach(function(t,n){if(n>0){var i=F[n-1],r=E[i.a],s=E[i.b];r.size=e[n-1],s.size=t,z(r.element,r.size,i.aGutterSize),z(s.element,s.size,i.bGutterSize)}})}function p(){F.forEach(function(e){e.parent.removeChild(e.gutter),E[e.a].element.style[y]="",E[e.b].element.style[y]=""})}void 0===c&&(c={});var y,b,G,E,w=l(u[0]).parentNode,D=e.getComputedStyle(w).flexDirection,U=c.sizes||u.map(function(){return 100/u.length}),k=void 0!==c.minSize?c.minSize:100,x=Array.isArray(k)?k:u.map(function(){return k}),L=void 0!==c.gutterSize?c.gutterSize:10,M=void 0!==c.snapOffset?c.snapOffset:30,O=c.direction||"horizontal",j=c.cursor||("horizontal"===O?"ew-resize":"ns-resize"),C=c.gutter||function(e,n){var i=t.createElement("div");return i.className="gutter gutter-"+n,i},A=c.elementStyle||function(e,t,n){var i={};return"string"==typeof t||t instanceof String?i[e]=t:i[e]=o?t+"%":a+"("+t+"% - "+n+"px)",i},B=c.gutterStyle||function(e,t){return n={},n[e]=t+"px",n;var n};"horizontal"===O?(y="width","clientWidth",b="clientX",G="left","paddingLeft"):"vertical"===O&&(y="height","clientHeight",b="clientY",G="top","paddingTop");var F=[];return E=u.map(function(e,t){var i,s={element:l(e),size:U[t],minSize:x[t]};if(t>0&&(i={a:t-1,b:t,dragging:!1,isFirst:1===t,isLast:t===u.length-1,direction:O,parent:w},i.aGutterSize=L,i.bGutterSize=L,i.isFirst&&(i.aGutterSize=L/2),i.isLast&&(i.bGutterSize=L/2),"row-reverse"===D||"column-reverse"===D)){var a=i.a;i.a=i.b,i.b=a}if(!o&&t>0){var c=C(t,O);h(c,L),c[n]("mousedown",S.bind(i)),c[n]("touchstart",S.bind(i)),w.insertBefore(c,s.element),i.gutter=c}0===t||t===u.length-1?z(s.element,s.size,L/2):z(s.element,s.size,L);var f=s.element[r]()[y];return f<s.minSize&&(s.minSize=f),t>0&&F.push(i),s}),o?{setSizes:v,destroy:p}:{setSizes:v,getSizes:function(){return E.map(function(e){return e.size})},collapse:function(e){if(e===F.length){var t=F[e-1];g.call(t),o||f.call(t,t.size-t.bGutterSize)}else{var n=F[e];g.call(n),o||f.call(n,n.aGutterSize)}},destroy:p}}});

///////////////////////////////////////////////

///////////////////////////////////////////////
// Copyright (c) 2013 Pieroxy <pieroxy@pieroxy.net>
// This work is free. You can redistribute it and/or modify it
// under the terms of the WTFPL, Version 2
// For more information see LICENSE.txt or http://www.wtfpl.net/
//
// For more information, the home page:
// http://pieroxy.net/blog/pages/lz-string/testing.html
//
// LZ-based compression algorithm, version 1.4.4
var LZString=function(){var o=String.fromCharCode,i={};var n={decompressFromBase64:function(o){return null==o?"":""==o?null:n._decompress(o.length,32,function(n){return function(o,n){if(!i[o]){i[o]={};for(var t=0;t<o.length;t++)i[o][o.charAt(t)]=t}return i[o][n]}("ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/=",o.charAt(n))})},_decompress:function(i,n,t){var r,e,a,s,p,u,l,f=[],c=4,d=4,h=3,v="",g=[],m={val:t(0),position:n,index:1};for(r=0;r<3;r+=1)f[r]=r;for(a=0,p=Math.pow(2,2),u=1;u!=p;)s=m.val&m.position,m.position>>=1,0==m.position&&(m.position=n,m.val=t(m.index++)),a|=(s>0?1:0)*u,u<<=1;switch(a){case 0:for(a=0,p=Math.pow(2,8),u=1;u!=p;)s=m.val&m.position,m.position>>=1,0==m.position&&(m.position=n,m.val=t(m.index++)),a|=(s>0?1:0)*u,u<<=1;l=o(a);break;case 1:for(a=0,p=Math.pow(2,16),u=1;u!=p;)s=m.val&m.position,m.position>>=1,0==m.position&&(m.position=n,m.val=t(m.index++)),a|=(s>0?1:0)*u,u<<=1;l=o(a);break;case 2:return""}for(f[3]=l,e=l,g.push(l);;){if(m.index>i)return"";for(a=0,p=Math.pow(2,h),u=1;u!=p;)s=m.val&m.position,m.position>>=1,0==m.position&&(m.position=n,m.val=t(m.index++)),a|=(s>0?1:0)*u,u<<=1;switch(l=a){case 0:for(a=0,p=Math.pow(2,8),u=1;u!=p;)s=m.val&m.position,m.position>>=1,0==m.position&&(m.position=n,m.val=t(m.index++)),a|=(s>0?1:0)*u,u<<=1;f[d++]=o(a),l=d-1,c--;break;case 1:for(a=0,p=Math.pow(2,16),u=1;u!=p;)s=m.val&m.position,m.position>>=1,0==m.position&&(m.position=n,m.val=t(m.index++)),a|=(s>0?1:0)*u,u<<=1;f[d++]=o(a),l=d-1,c--;break;case 2:return g.join("")}if(0==c&&(c=Math.pow(2,h),h++),f[l])v=f[l];else{if(l!==d)return null;v=e+e.charAt(0)}g.push(v),f[d++]=e+v.charAt(0),e=v,0==--c&&(c=Math.pow(2,h),h++)}}};return n}();"function"==typeof define&&define.amd?define(function(){return LZString}):"undefined"!=typeof module&&null!=module?module.exports=LZString:"undefined"!=typeof angular&&null!=angular&&angular.module("LZString",[]).factory("LZString",function(){return LZString});
///////////////////////////////////////////////

///////////////////////////////////////////////
/*!
* PEP v0.4.3 | https://github.com/jquery/PEP
* Copyright jQuery Foundation and other contributors | http://jquery.org/license
  */
  !function(a,b){"object"==typeof exports&&"undefined"!=typeof module?module.exports=b():"function"==typeof define&&define.amd?define(b):a.PointerEventsPolyfill=b()}(this,function(){"use strict";function a(a,b){b=b||Object.create(null);var c=document.createEvent("Event");c.initEvent(a,b.bubbles||!1,b.cancelable||!1);
  for(var d,e=2;e<m.length;e++)d=m[e],c[d]=b[d]||n[e];c.buttons=b.buttons||0;
  var f=0;return f=b.pressure&&c.buttons?b.pressure:c.buttons?.5:0,c.x=c.clientX,c.y=c.clientY,c.pointerId=b.pointerId||0,c.width=b.width||0,c.height=b.height||0,c.pressure=f,c.tiltX=b.tiltX||0,c.tiltY=b.tiltY||0,c.twist=b.twist||0,c.tangentialPressure=b.tangentialPressure||0,c.pointerType=b.pointerType||"",c.hwTimestamp=b.hwTimestamp||0,c.isPrimary=b.isPrimary||!1,c}function b(){this.array=[],this.size=0}function c(a,b,c,d){this.addCallback=a.bind(d),this.removeCallback=b.bind(d),this.changedCallback=c.bind(d),A&&(this.observer=new A(this.mutationWatcher.bind(this)))}function d(a){return"body /shadow-deep/ "+e(a)}function e(a){return'[touch-action="'+a+'"]'}function f(a){return"{ -ms-touch-action: "+a+"; touch-action: "+a+"; }"}function g(){if(F){D.forEach(function(a){String(a)===a?(E+=e(a)+f(a)+"\n",G&&(E+=d(a)+f(a)+"\n")):(E+=a.selectors.map(e)+f(a.rule)+"\n",G&&(E+=a.selectors.map(d)+f(a.rule)+"\n"))});var a=document.createElement("style");a.textContent=E,document.head.appendChild(a)}}function h(){if(!window.PointerEvent){if(window.PointerEvent=a,window.navigator.msPointerEnabled){var b=window.navigator.msMaxTouchPoints;Object.defineProperty(window.navigator,"maxTouchPoints",{value:b,enumerable:!0}),u.registerSource("ms",_)}else Object.defineProperty(window.navigator,"maxTouchPoints",{value:0,enumerable:!0}),u.registerSource("mouse",N),void 0!==window.ontouchstart&&u.registerSource("touch",V);u.register(document)}}function i(a){if(!u.pointermap.has(a)){var b=new Error("InvalidPointerId");throw b.name="InvalidPointerId",b}}function j(a){for(var b=a.parentNode;b&&b!==a.ownerDocument;)b=b.parentNode;if(!b){var c=new Error("InvalidStateError");throw c.name="InvalidStateError",c}}function k(a){var b=u.pointermap.get(a);return 0!==b.buttons}function l(){window.Element&&!Element.prototype.setPointerCapture&&Object.defineProperties(Element.prototype,{setPointerCapture:{value:W},releasePointerCapture:{value:X},hasPointerCapture:{value:Y}})}
  var m=["bubbles","cancelable","view","detail","screenX","screenY","clientX","clientY","ctrlKey","altKey","shiftKey","metaKey","button","relatedTarget","pageX","pageY"],n=[!1,!1,null,null,0,0,0,0,!1,!1,!1,!1,0,null,0,0],o=window.Map&&window.Map.prototype.forEach,p=o?Map:b;b.prototype={set:function(a,b){return void 0===b?this["delete"](a):(this.has(a)||this.size++,void(this.array[a]=b))},has:function(a){return void 0!==this.array[a]},"delete":function(a){this.has(a)&&(delete this.array[a],this.size--)},get:function(a){return this.array[a]},clear:function(){this.array.length=0,this.size=0},forEach:function(a,b){return this.array.forEach(function(c,d){a.call(b,c,d,this)},this)}};var q=["bubbles","cancelable","view","detail","screenX","screenY","clientX","clientY","ctrlKey","altKey","shiftKey","metaKey","button","relatedTarget","buttons","pointerId","width","height","pressure","tiltX","tiltY","pointerType","hwTimestamp","isPrimary","type","target","currentTarget","which","pageX","pageY","timeStamp"],r=[!1,!1,null,null,0,0,0,0,!1,!1,!1,!1,0,null,0,0,0,0,0,0,0,"",0,!1,"",null,null,0,0,0,0],s={pointerover:1,pointerout:1,pointerenter:1,pointerleave:1},t="undefined"!=typeof SVGElementInstance,u={pointermap:new p,eventMap:Object.create(null),captureInfo:Object.create(null),eventSources:Object.create(null),eventSourceList:[],registerSource:function(a,b){var c=b,d=c.events;d&&(d.forEach(function(a){c[a]&&(this.eventMap[a]=c[a].bind(c))},this),this.eventSources[a]=c,this.eventSourceList.push(c))},register:function(a){for(var b,c=this.eventSourceList.length,d=0;d<c&&(b=this.eventSourceList[d]);d++)
  b.register.call(b,a)},unregister:function(a){for(var b,c=this.eventSourceList.length,d=0;d<c&&(b=this.eventSourceList[d]);d++)
  b.unregister.call(b,a)},contains:function(a,b){try{return a.contains(b)}catch(c){return!1}},down:function(a){a.bubbles=!0,this.fireEvent("pointerdown",a)},move:function(a){a.bubbles=!0,this.fireEvent("pointermove",a)},up:function(a){a.bubbles=!0,this.fireEvent("pointerup",a)},enter:function(a){a.bubbles=!1,this.fireEvent("pointerenter",a)},leave:function(a){a.bubbles=!1,this.fireEvent("pointerleave",a)},over:function(a){a.bubbles=!0,this.fireEvent("pointerover",a)},out:function(a){a.bubbles=!0,this.fireEvent("pointerout",a)},cancel:function(a){a.bubbles=!0,this.fireEvent("pointercancel",a)},leaveOut:function(a){this.out(a),this.propagate(a,this.leave,!1)},enterOver:function(a){this.over(a),this.propagate(a,this.enter,!0)},eventHandler:function(a){if(!a._handledByPE){var b=a.type,c=this.eventMap&&this.eventMap[b];c&&c(a),a._handledByPE=!0}},listen:function(a,b){b.forEach(function(b){this.addEvent(a,b)},this)},unlisten:function(a,b){b.forEach(function(b){this.removeEvent(a,b)},this)},addEvent:function(a,b){a.addEventListener(b,this.boundHandler)},removeEvent:function(a,b){a.removeEventListener(b,this.boundHandler)},makeEvent:function(b,c){this.captureInfo[c.pointerId]&&(c.relatedTarget=null);var d=new a(b,c);return c.preventDefault&&(d.preventDefault=c.preventDefault),d._target=d._target||c.target,d},fireEvent:function(a,b){var c=this.makeEvent(a,b);return this.dispatchEvent(c)},cloneEvent:function(a){for(var b,c=Object.create(null),d=0;d<q.length;d++)b=q[d],c[b]=a[b]||r[d],!t||"target"!==b&&"relatedTarget"!==b||c[b]instanceof SVGElementInstance&&(c[b]=c[b].correspondingUseElement);return a.preventDefault&&(c.preventDefault=function(){a.preventDefault()}),c},getTarget:function(a){var b=this.captureInfo[a.pointerId];return b?a._target!==b&&a.type in s?void 0:b:a._target},propagate:function(a,b,c){for(var d=a.target,e=[];d!==document&&!d.contains(a.relatedTarget);) if(e.push(d),d=d.parentNode,!d)return;c&&e.reverse(),e.forEach(function(c){a.target=c,b.call(this,a)},this)},setCapture:function(b,c,d){this.captureInfo[b]&&this.releaseCapture(b,d),this.captureInfo[b]=c,this.implicitRelease=this.releaseCapture.bind(this,b,d),document.addEventListener("pointerup",this.implicitRelease),document.addEventListener("pointercancel",this.implicitRelease);var e=new a("gotpointercapture");e.pointerId=b,e._target=c,d||this.asyncDispatchEvent(e)},releaseCapture:function(b,c){var d=this.captureInfo[b];if(d){this.captureInfo[b]=void 0,document.removeEventListener("pointerup",this.implicitRelease),document.removeEventListener("pointercancel",this.implicitRelease);var e=new a("lostpointercapture");e.pointerId=b,e._target=d,c||this.asyncDispatchEvent(e)}},dispatchEvent:/*scope.external.dispatchEvent || */function(a){var b=this.getTarget(a);if(b)return b.dispatchEvent(a)},asyncDispatchEvent:function(a){requestAnimationFrame(this.dispatchEvent.bind(this,a))}};u.boundHandler=u.eventHandler.bind(u);var v={shadow:function(a){if(a)return a.shadowRoot||a.webkitShadowRoot},canTarget:function(a){return a&&Boolean(a.elementFromPoint)},targetingShadow:function(a){var b=this.shadow(a);if(this.canTarget(b))return b},olderShadow:function(a){var b=a.olderShadowRoot;if(!b){var c=a.querySelector("shadow");c&&(b=c.olderShadowRoot)}return b},allShadows:function(a){for(var b=[],c=this.shadow(a);c;)b.push(c),c=this.olderShadow(c);return b},searchRoot:function(a,b,c){if(a){var d,e,f=a.elementFromPoint(b,c);for(e=this.targetingShadow(f);e;){if(d=e.elementFromPoint(b,c)){var g=this.targetingShadow(d);return this.searchRoot(g,b,c)||d} e=this.olderShadow(e)} return f}},owner:function(a){
  for(var b=a;b.parentNode;)b=b.parentNode;
  return b.nodeType!==Node.DOCUMENT_NODE&&b.nodeType!==Node.DOCUMENT_FRAGMENT_NODE&&(b=document),b},findTarget:function(a){var b=a.clientX,c=a.clientY,d=this.owner(a.target);
  return d.elementFromPoint(b,c)||(d=document),this.searchRoot(d,b,c)}},w=Array.prototype.forEach.call.bind(Array.prototype.forEach),x=Array.prototype.map.call.bind(Array.prototype.map),y=Array.prototype.slice.call.bind(Array.prototype.slice),z=Array.prototype.filter.call.bind(Array.prototype.filter),A=window.MutationObserver||window.WebKitMutationObserver,B="[touch-action]",C={subtree:!0,childList:!0,attributes:!0,attributeOldValue:!0,attributeFilter:["touch-action"]};c.prototype={watchSubtree:function(a){
  //
  this.observer&&v.canTarget(a)&&this.observer.observe(a,C)},enableOnSubtree:function(a){this.watchSubtree(a),a===document&&"complete"!==document.readyState?this.installOnLoad():this.installNewSubtree(a)},installNewSubtree:function(a){w(this.findElements(a),this.addElement,this)},findElements:function(a){return a.querySelectorAll?a.querySelectorAll(B):[]},removeElement:function(a){this.removeCallback(a)},addElement:function(a){this.addCallback(a)},elementChanged:function(a,b){this.changedCallback(a,b)},concatLists:function(a,b){return a.concat(y(b))},
  installOnLoad:function(){document.addEventListener("readystatechange",function(){"complete"===document.readyState&&this.installNewSubtree(document)}.bind(this))},isElement:function(a){return a.nodeType===Node.ELEMENT_NODE},flattenMutationTree:function(a){
  var b=x(a,this.findElements,this);
  return b.push(z(a,this.isElement)),b.reduce(this.concatLists,[])},mutationWatcher:function(a){a.forEach(this.mutationHandler,this)},mutationHandler:function(a){if("childList"===a.type){var b=this.flattenMutationTree(a.addedNodes);b.forEach(this.addElement,this);var c=this.flattenMutationTree(a.removedNodes);c.forEach(this.removeElement,this)}else"attributes"===a.type&&this.elementChanged(a.target,a.oldValue)}};var D=["none","auto","pan-x","pan-y",{rule:"pan-x pan-y",selectors:["pan-x pan-y","pan-y pan-x"]}],E="",F=window.PointerEvent||window.MSPointerEvent,G=!window.ShadowDOMPolyfill&&document.head.createShadowRoot,H=u.pointermap,I=25,J=[1,4,2,8,16],K=!1;try{K=1===new MouseEvent("test",{buttons:1}).buttons}catch(L){}
  var M,N={POINTER_ID:1,POINTER_TYPE:"mouse",events:["mousedown","mousemove","mouseup","mouseover","mouseout"],register:function(a){u.listen(a,this.events)},unregister:function(a){u.unlisten(a,this.events)},lastTouches:[],
  isEventSimulatedFromTouch:function(a){for(var b,c=this.lastTouches,d=a.clientX,e=a.clientY,f=0,g=c.length;f<g&&(b=c[f]);f++){
  var h=Math.abs(d-b.x),i=Math.abs(e-b.y);if(h<=I&&i<=I)return!0}},prepareEvent:function(a){var b=u.cloneEvent(a),c=b.preventDefault;return b.preventDefault=function(){a.preventDefault(),c()},b.pointerId=this.POINTER_ID,b.isPrimary=!0,b.pointerType=this.POINTER_TYPE,b},prepareButtonsForMove:function(a,b){var c=H.get(this.POINTER_ID);
  0!==b.which&&c?a.buttons=c.buttons:a.buttons=0,b.buttons=a.buttons},mousedown:function(a){if(!this.isEventSimulatedFromTouch(a)){var b=H.get(this.POINTER_ID),c=this.prepareEvent(a);K||(c.buttons=J[c.button],b&&(c.buttons|=b.buttons),a.buttons=c.buttons),H.set(this.POINTER_ID,a),b&&0!==b.buttons?u.move(c):u.down(c)}},mousemove:function(a){if(!this.isEventSimulatedFromTouch(a)){var b=this.prepareEvent(a);K||this.prepareButtonsForMove(b,a),b.button=-1,H.set(this.POINTER_ID,a),u.move(b)}},mouseup:function(a){if(!this.isEventSimulatedFromTouch(a)){var b=H.get(this.POINTER_ID),c=this.prepareEvent(a);if(!K){var d=J[c.button];
  c.buttons=b?b.buttons&~d:0,a.buttons=c.buttons}H.set(this.POINTER_ID,a),
  c.buttons&=~J[c.button],0===c.buttons?u.up(c):u.move(c)}},mouseover:function(a){if(!this.isEventSimulatedFromTouch(a)){var b=this.prepareEvent(a);K||this.prepareButtonsForMove(b,a),b.button=-1,H.set(this.POINTER_ID,a),u.enterOver(b)}},mouseout:function(a){if(!this.isEventSimulatedFromTouch(a)){var b=this.prepareEvent(a);K||this.prepareButtonsForMove(b,a),b.button=-1,u.leaveOut(b)}},cancel:function(a){var b=this.prepareEvent(a);u.cancel(b),this.deactivateMouse()},deactivateMouse:function(){H["delete"](this.POINTER_ID)}},O=u.captureInfo,P=v.findTarget.bind(v),Q=v.allShadows.bind(v),R=u.pointermap,S=2500,T=200,U="touch-action",V={events:["touchstart","touchmove","touchend","touchcancel"],register:function(a){M.enableOnSubtree(a)},unregister:function(){},elementAdded:function(a){var b=a.getAttribute(U),c=this.touchActionToScrollType(b);c&&(a._scrollType=c,u.listen(a,this.events),
  Q(a).forEach(function(a){a._scrollType=c,u.listen(a,this.events)},this))},elementRemoved:function(a){a._scrollType=void 0,u.unlisten(a,this.events),
  Q(a).forEach(function(a){a._scrollType=void 0,u.unlisten(a,this.events)},this)},elementChanged:function(a,b){var c=a.getAttribute(U),d=this.touchActionToScrollType(c),e=this.touchActionToScrollType(b);
  d&&e?(a._scrollType=d,Q(a).forEach(function(a){a._scrollType=d},this)):e?this.elementRemoved(a):d&&this.elementAdded(a)},scrollTypes:{EMITTER:"none",XSCROLLER:"pan-x",YSCROLLER:"pan-y",SCROLLER:/^(?:pan-x pan-y)|(?:pan-y pan-x)|auto$/},touchActionToScrollType:function(a){var b=a,c=this.scrollTypes;return"none"===b?"none":b===c.XSCROLLER?"X":b===c.YSCROLLER?"Y":c.SCROLLER.exec(b)?"XY":void 0},POINTER_TYPE:"touch",firstTouch:null,isPrimaryTouch:function(a){return this.firstTouch===a.identifier},setPrimaryTouch:function(a){
  (0===R.size||1===R.size&&R.has(1))&&(this.firstTouch=a.identifier,this.firstXY={X:a.clientX,Y:a.clientY},this.scrolling=!1,this.cancelResetClickCount())},removePrimaryPointer:function(a){a.isPrimary&&(this.firstTouch=null,this.firstXY=null,this.resetClickCount())},clickCount:0,resetId:null,resetClickCount:function(){var a=function(){this.clickCount=0,this.resetId=null}.bind(this);this.resetId=setTimeout(a,T)},cancelResetClickCount:function(){this.resetId&&clearTimeout(this.resetId)},typeToButtons:function(a){var b=0;return"touchstart"!==a&&"touchmove"!==a||(b=1),b},touchToPointer:function(a){var b=this.currentTouchEvent,c=u.cloneEvent(a),d=c.pointerId=a.identifier+2;c.target=O[d]||P(c),c.bubbles=!0,c.cancelable=!0,c.detail=this.clickCount,c.button=0,c.buttons=this.typeToButtons(b.type),c.width=2*(a.radiusX||a.webkitRadiusX||0),c.height=2*(a.radiusY||a.webkitRadiusY||0),c.pressure=a.force||a.webkitForce||.5,c.isPrimary=this.isPrimaryTouch(a),c.pointerType=this.POINTER_TYPE,
  c.altKey=b.altKey,c.ctrlKey=b.ctrlKey,c.metaKey=b.metaKey,c.shiftKey=b.shiftKey;
  var e=this;return c.preventDefault=function(){e.scrolling=!1,e.firstXY=null,b.preventDefault()},c},processTouches:function(a,b){var c=a.changedTouches;this.currentTouchEvent=a;for(var d,e=0;e<c.length;e++)d=c[e],b.call(this,this.touchToPointer(d))},
  shouldScroll:function(a){if(this.firstXY){var b,c=a.currentTarget._scrollType;if("none"===c)
  b=!1;else if("XY"===c)
  b=!0;else{var d=a.changedTouches[0],e=c,f="Y"===c?"X":"Y",g=Math.abs(d["client"+e]-this.firstXY[e]),h=Math.abs(d["client"+f]-this.firstXY[f]);
  b=g>=h}return this.firstXY=null,b}},findTouch:function(a,b){for(var c,d=0,e=a.length;d<e&&(c=a[d]);d++)if(c.identifier===b)return!0},
  vacuumTouches:function(a){var b=a.touches;
  if(R.size>=b.length){var c=[];R.forEach(function(a,d){
  if(1!==d&&!this.findTouch(b,d-2)){var e=a.out;c.push(e)}},this),c.forEach(this.cancelOut,this)}},touchstart:function(a){this.vacuumTouches(a),this.setPrimaryTouch(a.changedTouches[0]),this.dedupSynthMouse(a),this.scrolling||(this.clickCount++,this.processTouches(a,this.overDown))},overDown:function(a){R.set(a.pointerId,{target:a.target,out:a,outTarget:a.target}),u.enterOver(a),u.down(a)},touchmove:function(a){this.scrolling||(this.shouldScroll(a)?(this.scrolling=!0,this.touchcancel(a)):(a.preventDefault(),this.processTouches(a,this.moveOverOut)))},moveOverOut:function(a){var b=a,c=R.get(b.pointerId);
  if(c){var d=c.out,e=c.outTarget;u.move(b),d&&e!==b.target&&(d.relatedTarget=b.target,b.relatedTarget=e,
  d.target=e,b.target?(u.leaveOut(d),u.enterOver(b)):(
  b.target=e,b.relatedTarget=null,this.cancelOut(b))),c.out=b,c.outTarget=b.target}},touchend:function(a){this.dedupSynthMouse(a),this.processTouches(a,this.upOut)},upOut:function(a){this.scrolling||(u.up(a),u.leaveOut(a)),this.cleanUpPointer(a)},touchcancel:function(a){this.processTouches(a,this.cancelOut)},cancelOut:function(a){u.cancel(a),u.leaveOut(a),this.cleanUpPointer(a)},cleanUpPointer:function(a){R["delete"](a.pointerId),this.removePrimaryPointer(a)},
  dedupSynthMouse:function(a){var b=N.lastTouches,c=a.changedTouches[0];
  if(this.isPrimaryTouch(c)){
  var d={x:c.clientX,y:c.clientY};b.push(d);var e=function(a,b){var c=a.indexOf(b);c>-1&&a.splice(c,1)}.bind(null,b,d);setTimeout(e,S)}}};M=new c(V.elementAdded,V.elementRemoved,V.elementChanged,V);var W,X,Y,Z=u.pointermap,$=window.MSPointerEvent&&"number"==typeof window.MSPointerEvent.MSPOINTER_TYPE_MOUSE,_={events:["MSPointerDown","MSPointerMove","MSPointerUp","MSPointerOut","MSPointerOver","MSPointerCancel","MSGotPointerCapture","MSLostPointerCapture"],register:function(a){u.listen(a,this.events)},unregister:function(a){u.unlisten(a,this.events)},POINTER_TYPES:["","unavailable","touch","pen","mouse"],prepareEvent:function(a){var b=a;return $&&(b=u.cloneEvent(a),b.pointerType=this.POINTER_TYPES[a.pointerType]),b},cleanup:function(a){Z["delete"](a)},MSPointerDown:function(a){Z.set(a.pointerId,a);var b=this.prepareEvent(a);u.down(b)},MSPointerMove:function(a){var b=this.prepareEvent(a);u.move(b)},MSPointerUp:function(a){var b=this.prepareEvent(a);u.up(b),this.cleanup(a.pointerId)},MSPointerOut:function(a){var b=this.prepareEvent(a);u.leaveOut(b)},MSPointerOver:function(a){var b=this.prepareEvent(a);u.enterOver(b)},MSPointerCancel:function(a){var b=this.prepareEvent(a);u.cancel(b),this.cleanup(a.pointerId)},MSLostPointerCapture:function(a){var b=u.makeEvent("lostpointercapture",a);u.dispatchEvent(b)},MSGotPointerCapture:function(a){var b=u.makeEvent("gotpointercapture",a);u.dispatchEvent(b)}},aa=window.navigator;aa.msPointerEnabled?(W=function(a){i(a),j(this),k(a)&&(u.setCapture(a,this,!0),this.msSetPointerCapture(a))},X=function(a){i(a),u.releaseCapture(a,!0),this.msReleasePointerCapture(a)}):(W=function(a){i(a),j(this),k(a)&&u.setCapture(a,this)},X=function(a){i(a),u.releaseCapture(a)}),Y=function(a){return!!u.captureInfo[a]},g(),h(),l();var ba={dispatcher:u,Installer:c,PointerEvent:a,PointerMap:p,targetFinding:v};return ba});

///////////////////////////////////////////////

///////////////////////////////////////////////
var config = {"dark_mode": false, "show_pads": true, "show_fabrication": false, "show_silkscreen": true, "highlight_pin1": false, "redraw_on_drag": true, "board_rotation": 0, "checkboxes": "Sourced,Placed", "bom_view": "left-right", "layer_view": "FB", "fields": ["Value", "Footprint"]}
///////////////////////////////////////////////

///////////////////////////////////////////////
var pcbdata = JSON.parse(LZString.decompressFromBase64("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DJjwE/bOqTT26kVNjMyGA7FKotYmB+7IKou8UL6EHzSG6bFByj0k1GMEyovl6kvlEuPyedF8ot9znPnIkovgPFuwMEopRQ3+jiiopg7ylTmlNhPnLtzi3MCfnPiopYoowop6oqCpECwNSouZLLmotlw1VumbkN8yE4kFyorIopswMAXJGoozkBKopIUMFqlzKAqov2ot6ovXEySgVqoskLEO+AaorB0KaotfEBaooi8NUQlQXIArP6+RIXPnIrFmCSKHxwJjItMKkLBHJwP3LIeopxwKkAp9gw+osHIpTUPeooIXNxwL+op+ov6gp/6LpanTsguSMoFIygNhoph5LtEL+RPhMLF5Ng2NE5heSPxakfUBA4PH5P9uCehKnyDE4Lpak74IhYK/YNeuERop3e3bSLJooxot44KxovQqGhSPD5JZuFd3HkJKMJLpakHehu0K55LpakTYk2fxXSLpakf+Co4O5JIygKBck55P95JramPAlE/1tJJhovyhOkJIZot6yAE4LRotlooJ5KuJMloqZSPh4IygKtCHl5I/5OBB3hZNf5MvqHy4OFSLyTxUaDV5MduDZoo40Ir5IygO9EWZovfSJZuG+pFE4OfSJhVAl5KVSKposa4L9SJvOwxoqgjHidnuyyzSOb5JdKIyJJloojSHd5IlooNoq95I5ooTuCcyKKJMduCFoqD5NY4LpanVopm0INSOVopqJLSJJhordoq9SMcVwVouaJMT5PmTylopT5LVorFoq6JKtEMjouKfy9al1opO0O4FJnKAL5MOJNZoq+hJy4MduAtovzopQ2JtopzoqdooT5MwqxDuHSaE2LP0IT+qPTos2JL7SLQ+E75NrSMduAti175IrBwToobSNTSO7ouH5ODuAnorm4IzuAXRMn5NeSNFopn5M7ooN+PtoqZgNf5NXosZlN4yOtooO4Pv5MZotSK3mZk6T1o8laWKQFM5ovHVHq3x5ovpuELopP5I/O0sEINgIv5O6BxiCLAyIRooxosRJI9axRosf5IVuDnorfSPFSLcR3f5KnorpVC/5OfSLi1F/5MJotFuH5hPjgIV5LsiBAFLNos5osNoppJNgu2jOGgFN3oqgYrgFK94LpalvRLJ4PvouJGFgyO6hxDa3JosQyNduG7opwFIdZg3ot2WMwyObooN4LRotIYvYFIQYq5ovnDnhotg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oJ0oUMq3aHFKk450X0vvMutMrEWCfMpkgBfMo30ta0vfMv4suH0sEsoT0qnMv9MtnMvQspdUvP0pDMsv0vO0p6OPwsszUrRUq9u1F2H951Isp3MvjMrmHn3MrS0oRtG7gy+0qy0tPMqAMuzMovMp2/CSECi8O+ziwGCkso70pN0sXgzksvm0u4stfMpt0rtUDR0s9MpiMp9MqbMr/MpbMp10oqUtMsrj507Km8soFOk70sfMrwgC4sqt0pgsuHSB00tUsq9MsFMo0ss50q0srT0vnMuRUqwssJAE9QEMsvTUqf0uIQFir0gGAkhHQVBL0sMACLUu+Upsssb3ju5hr0vrACrUvTMvV0pHAE10v/MpisvyZGqssjQ3Q3CkspXxhosqY1EgsufMugsuHMtgsrkfCyst1MobMuEssn0pcsoAsui0rjdMA8GasvUxGjhF8svseHGsvkssmsvp0pmstCstj0q/Mtysr9MvyspHADnMowsuKsr0sqsAEu0thUsEACMstEm3s0EOQFaTFjMssstj0RejzOMrssrasvX9josu6sqzMvPMuWsrp0m45O7GBestAsoD0t7Mpw0vxUrSssrMqmssyssOsvrMqQsoWsvuMqWsr6sodfDxoC46DOQDXo0SsuN0srUv8sup0sCssUspR0r4svgsoEspyst20ryspT0oKsv+stO0vaAAu0vXkof0oqsrXMqqsvzdKNY02lwssoasrp/HyIkospasp70WPMscss6srPMtEsui0pZsuhSnWssgmE2sogsrxstD0oJsoysvJEAOsp30rCsopMoisuhMvaAAYstWMr8rx2lx5ulYss7UpvWy2svmAGD0omsplsthsrlsoQ/PhssQspOsqT0s0svOsu0soTUt0stpsoF0oAABEc6oHrKrhJEWYr+99aj2bKqQBbTkTeEpypDdLFRsQww+bKOrLgNgMzK/rK1bKdvxHWY1UBbeIxbKyMCDwBJbLUrLDbL0rLjbKzmgzbLjrKhLLmjLFrKAbLUbK7Wga8so7LubLtZVAAQ47L+zKE7KYbLiRNlLKSbLsrLwrLjNKorKUbLGLKGHFDkBc7KwbKiMDY7LodKDbLdrKjbLS7LibL1gAELLU7L1LLq7LM7La7L4XFnrLKNRo7LyZsLHFKdLi7KeLLgrLNrgU7K1LK2dK+7KhbLXbKa8tm/sR7KH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SsASvRisySpRSqd8qJSodfCZStFHPJSoM0FxSppSvxSuQSrOSvySovitC0uF0tuSsRMuklKQWFpHwISt3MtuGXWsuR8FddE0SvISsmSqUgFDIOd/NpHyksvYsp3iv8SsOSs3sqUspOStVcqsSuhSucMtlSpt/NGir1StMcoNStLiqNSqJsoXirpSrFSrQSs6StkCsCUtkSsUCr22E4kGgKGoUoISt4EK6iuKiqf8F6isnZnVSp5Su/VBsKHugGPVAsCrqMoOSp+Mr6CqI0rmiuwct6UtcCu8DXfo2nUp1uR+0m8CuHqU2ivEXhvGlyj2l+GCCqXug3UvgxnCCqxHBOiqzJVuiseCv5ivU0t5iuuir2Uov2jfInPUo4Wkeiursmeish0VeiqyCt6tA+ivEcufUu+iraukKCpRiGKCs/UsBiuWHzDUUGCspios5B1io9xADxBDkhNSt7crNSrICoUMp9SvzmGoUosCpRivZSuRSosSpACsGiqHoF9SujSocipQcvZStJivsCrvRQnSuUcuGCtb7kcwlpiso0omCvfUymCq+7lZUrccrZitjMQ5itydi5ir5UtWCqmMvWCvAvHPJF+jGFisE0r2CqixilUslityJGOCvicoVUsScvpbOVUtScrAFBViu1UsWiucCsvBCwcqmhGnSuqCrxZHqCriStFSpySu+CuDcqs0tKcvNisBCvs0oWgDFgAoaAGfUaFEhOCdir+OBdir7tDdis0AH80pqio/sowSsYAGXMsaip6SoIMQWMVXo1yitxCpKNARZVvCpVSoy0shssHipDss/ivDSurGHV/y+RNoSptSuJipgCqCiqTsrqYHnSuhivYSthit0SuFeOt/0kyutSvAsqEysVcrkyrcirv8vrcpdSsYypiipYytv0ruspuSvYyruLDGHC3Mp4yu4AWEPHPkSzIjzssbpzQLACACYLCAIVDSraSpwytQSqMypKssYAAMsvkCt0iv/6HM+GIsoO/AVSqssvJsmVSvDioLADVSo/iqXSsesqCyvzmKAzB08qLiuSsrGsp0yqESuOSqdSvoCsXSuxiodfHiypXIDwKz2Sohsv1SpX8t0yvLisUyrOcsMyo0ip8yqv0vpsoCyq6yBALkWphv9jyiv+7D4yoiyuosv4Sv5su+Sp0Ss4SsPNgayoMmKSyukssCivSyuNSsyyss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rWYuWW/qoga43KsAa8/qlnygJqvAal1jVg9DfqjAa2jqs/q+AK8nq5fqw82afqlpnKga9/qtga/tqjgajXK0gay/q8h0l1jT3s6gaphgYga0HqvfqmFK8Qamrvfgau8ykAa9gaugazgarnq7ga8gasuWX64IAaqfGOAamXqr/qxAaiAanHqinqpgazDipQa8rSlQaoQatQakQasLqsgaswagkoCwa7FSqwagwahuq7HquQa0SbMcIFKANVMQga6QazAaowavwq3Aa6AauCeBWxVgamgaz/qtwakgauway/q3GcXuuUIaqQal+q4Dqi3S4Qax/qxnqw8gMuWHwa0aKlwapIawwa9wa3AalvXOIat/q5Qa/QanIayIa2Qa5Aaqe07Qa+OiXwaxIa5tqn7KgIanAap/qlhYA/qwoa3QaxbYEoaogK+oavIapoaz7k+xLNGctoan9UQQauCqsoahnq+9qsR7DIawp8GoawOq8JqlIapAanoa4+AXgaxQagYa2CecIa6warAa8AawIa+YangagYSCQapwa4Aajoagjq84qmwa1Ia+9qyoa5gavYavQaoYav5qroaqIayrq/4qs4au5TKEKPvK7IauoajJKhoa6HKrYagRcVUhQqwZYal4aw4am4a8oaz4a8YamAarIag4a6/ym0q2Ya4wavyq1Oq7MqwKqgyytjqk9ql5ijAYIsYa/KuMyrPqkAquxq7NaVcq31q+9qpEa5nUdVGEvq/ZK1+qwRKoXqivqmTqjzquTqvEao2o0+yl9qhvq21K+LqtTqkKK24a7JK6Rq/yq2Eay+KhEawPqthfKho4uWULK7uKgrKsOKkhK8fq9cq1TKh/gHka5YavhK2nq9nq3GTERKznqmNq/xq47qhF4bZUCUaiWytnqxkamUaocq+ga6Jqm4qtka4iqnMqgJSvMqx1qmOAPFYNbcfejPOqjqK+FhJ2kOYqu28WoalXSjBqyfq8yAE0awMcil6D7KroK1LKpkqk9KmaK6dmJNKpDKhaKp7MSkWZaKwhy0ZSts4daKiZSvP8PNKmZS3aKotKhCEEtKsIKo6KiIKitKvdSi/ab04bJyxIK+tK09SpIK5tK45SmtsJ6KjoaDtKvKLT+8e9SntKp9Sm1yftKmY4QdKxPuf6K/eonRaDofcdKqxyqdKvJyx6KCGKxfqqvqzQa7pgI9WY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ha1pamiaq3qhJa5BaiSqzpa+4ayZauPna0HPDqoBqqKa4LqmKajYa4JK9xawKqgJSwSav2K92YIf2QBy/xajQKkByrQKkAqgaa/hK7Ea9yaxUa0YiBBy0xayaa2NKgZamwKhGau9FFDK70ylwKpaaydSwMazwKrNKjaa3wKnZkJoUSMaqDGPaKhZSg6aptsI6axhyjhyytK5Ma1hyoQyy6akBdBtK+jhNK6Ty4e6ayIDXMaxpNZ6artK0RyvkUd6a3KwfIKgdK76aysa0nmY+o79S8oKn8ai9KsGKgVSuoK/WKuRa45q4Ra6vKzR8wxygFau8y2GarZasQq0FanilCmKzlagVkVGaxp4dGa+mKpcarE8HGatlSr1gDca0kC7lSj00fEhbmK/Fa06atYKk79as0NfzSma08apGac8a4DKiWKq8asDKxmayTSyDKlmai4KxWKjq4DmarlkV8a7marWK6tKvma3VamoKwWa7TSlvqmJq9cq4CamuKiWalC9M/yp5amRQTRK8EKo1ESEKzQ/ZWaxCaljSFMkGNSwpaiha8LS6yah5a+nUZXcYiypHQp2qxNhXpaw3St2qnvMXPqpZa/PqiiAfiksREHxKl3qoya8vq4iom3qyvqmxap+a9Nao7k5nKZ3q1K0aYatpai5asoReXqvZagiqr3qoiqlqanMq6fKhdqpTwa3fJ9hfWavNaQVND6yy+qrrDA8Ickq3JqmMqwecC5q4dar1y7e9AgqzQq7JattajNq3ea+QqqVq/Pq3dYBo0XpeV0qpXypda+uq4yakOqj3qtbqm5ahuK6BqrWak9qxCcZAoX5qUPnZBq0sqytqwTKhZa4aamtq0aa/VwESGcooHsqzJa/+jc5a5vqiqagValJaj9asZknyasqa49a9Tq4ZagpajWanMqgyy2Bq1NajpcRxOCc8EdanXqmvRPXqlAcfRa2SaupalJa+OWbAQvBkWOq5tay3q7ia63qjtanBa/ZawDauTqrOWKtmdiifDahYqsvq2iamIaatas9akZasdqmDqkKMkpamyalfAEA0LXql5azhxSzsF+K/Xq3KaldywxahvRVwPchqkIq+SK8ta+AawZatda09ajda+uaota0Tahta8TahxKyTa4Ya8DazkQddavlasQK5ja5PqwkAMLSq9arkasUfOLS7jqwJamwq/jqmwyb5ao3q35ap/ocbSpTq3yau1KviqmRay5ah+a9Fq8jaqsqozakrSvvK8Tq/WyhkaoZa3ianTapRaxgAGpynPK9ja+DanvExDa/xOK7KlQ7KhK7qK2sYKtwAtagqazQasTU9AQ/EwWhKi+yujanZau+yuTa1sa4Ka8LalLa8GbUaK9Laita2iarLarTar7q3HqvrKgHOAravvKoraqTazHqqey3Ja2wau4a8Hqyra8ecFeyguyjLaoja7eylea+9q5LavgQgWYNLa1eyzrax2a7rajda6EaxNanMqp9AdXqlrqEFU6KIfvqmzKliKmSFPXq0SDQaa+eDYTamFKp8gLlAObastaxGxI9axqapmq5JauTqkTOWba1BU83q4SKixarYq++avJaiDqqDaxRa6DqkzK5mAUxqlNaiBKnXi9BoAUGPka4nhfqa29MDua/Ka3OaiuquBy17aq/KsHy6oAcjy+lq/Wq7uasOa0Iyt2asakQeahiajUoc9ai7S1NAVPqqe4RrKnCatEa2ZajEampaoTarDaijalHawQ/XjqhyKqia1Sa8Jqyta5za67arSajwaipSvHasQwOvq7FSona8Eat+qnZasnapralka7tapPqwLawXS+OapJq6aQTrq+baruK/5GHuKwUa1qynOar2qqsqlaYZnqj0yj7K3WyqUapzalhKxJa9zqg5azzq4OjPKcR2gXhK6XatUa6KauXaztaxjq27aqDqz/KgJS5Ka+DanMPaGa5DazqKq0a2Lam0a5daxZaxLa4KaiMgTpAbqamNK/JDGTKtByuwKr0a54sH0aiFaxaa5TSpaKjwKmdSuFa8ZSzaaxdSihygtKoIKvaamMa9Fa90uexeLFa9MavFa79K1MaglauhFIlas9Su6a7MamNLARym9S/34Qsa7IKt6a4YDWXRKdlJS4RTZK5CA/8L9S15SwGa4phKoK6Va8GKnlajpatzazQa43am2K10aqO+Pba1xazYatIa8RQE3ax3aq3a8cayVa06JesalGaq9KucasYKjGaxxyxmKlVa59K/Ga19Kwma7xy7Vaz9Kvca/Va8mav9K41akWKr7bMWKwIRSUES1a2Jym8ao26NA+e8a6DKtmap8ap1av0awZShaarcET8a7AGFNKt4K9wa0+K0Wahcy8WaojKy2K5oawBqBvamTK3Nae2K+Cax2K9/auCaqEKpCatWalCau7az/Kmpyw3arFy/fOWIOUPqwtShOMXZudayszq/py3dqnEa2tqnTsRL88ckVnqoHqrrakja2Ka8lq2ta5ZaqWUbxbAooqL8qXq8bqlA6kbatA6q5aj4av1q9gOIWqTJwZA6wXqzLaoBa2da532egy+jCfnqgg66g61A62g60hq+g6+yMAwxJg63bqjXauXqtg6/0q8g6/dYaYcKg61wa9Ta4Xqsbav/qwQ69lRROtbg6mHqwg6+Ja4g6lza8ranrKqQ6zBjd11WQ69Hq0pq+rau0q4WayQ6jg6zBjHRsDQ6onqknakra/g6pia/Q6xdqdEEIw6mXaqTqxQ68na5raztqiw62tcaCqghzaXq8ua/yanQ6wEasg6wvtRA63HtPvKwHqlg6og6sw66vK1Q6lW4lw6zkzZg60Q6ytauw6lna/sanSa7A6zK4Sw68I6yKquQ6wI6hQ64I6zzqhI6/dYPzYEQ69w6xza2w6jI6ztqnw6neWdQ6/A6ng6+Q6mRamI6k4a+A6n7caQ6vA6l7qtw614ajw6jTC3Q6rYarI6+yMM6Vaw63g6rHq1o67w6hA6zg6+o6mLq17qqI60w63o62da4o6518Rg6so61I6kY6mg6yDatnatvqlja3zKyWAVPq3vgZO2A7fTPqjHaoJa5hageK19amda8jquChcpM9Za05asDa0naxrasFqxXaijatY66pMk5awnayRa4Fa1da/9asbahHagXSopKzggdXqnuuOCebHS0+qjfkNVJA89P7zSbyqeHXnyRwMoU6ATqt/KgLa+7ak/KrnawPqqaZAhK5aiXnbKOfAnAxfShjwJvcHSAbhsGo/WA6kTKl46+qKlcy57a7/yyXWEPWOcqstqtHbaOKGwqz5akXav1qz5wCAYId3dJawmKoFavI63oK13axNK+aa1WKr3atWKgMa33azNKh3keFa14cIPa/NKwIKqsEVFakIKuhystK6Paq6apMa1Ma86az1am6a06KhPa76Ue6Kslak5Sx6ayla29SrPa7tKnPar6K/Pah5S99SllakvahRy4GK9DK6carlatRysGawKanLa5ZasUYDAYIdKrsaqaapo6pAynva8lS6Vao062VagfaqsSY/pBcaoFhLGa5Vax9K1xy2LSCfazcaqdSafa7zhWfay6a+fagWKxfa0Jyqma01ammaznoOmasTS3noLfa2WK3faqMhR8ax1atVS51arma+aKmIKt1az1alwKy/a+Y61vq3Ua3taljq9qavTq5rxJOaswsnja3jKx9a1Bqlyapry9ba1IyznoRws2k6/vK4rapna8466xay46inq7xvNwsls67zai+DEw69s6q/aiE6z/KopKzbKu1AXbKw7KgzamyanjgU6XbXq67Kwk7OYq6oAe7KhLav7anSa2c6vpDUk6sHKxvUe/qmvahUa6vKjc6x62Wna5By8HK/wawo6nrK+r/MeCxHKmHas86gs6v1aos60ZaxgAB2yuDaszy97gSCs03azKa28KpnQVTa/RqnHalQ65CgaOqtoat/aqGgbBa9A60jq2va+I6llDRCskqakC60ha/za3Xa5jqhuKkLSrxamyakuANI+bt4Ezams6oJa8zan1qn5awVa8WsjC60Da7o6gKa23q806/Pq7QgdC6rkAOzamw6tta4c6hC67Tqveqp7a0La4WyjN0tygN4q/kaiLKoUa6Nyhs6vOKjN02xPaOy1LbGSazoakDq/ay2UasrauHat5q/Ry/N0qXoI2a4ay9Xats6rra+eK+C6hY6h86pY6vxSqhalKanuqziqtJqmObaxBROKlYwU2apxK386t9aiFqyuqr1suSqriqogZGi6p4652awFqkVq4FqyOasSqi46iC6huathasFXJyqhyKwOa1walVqiHaplq6Zqt2aqOaqEa6eq/OazYqAyqgOaqy6m5qrCKoVq3Zq+y6klqqyq1BoWHa6Iazlqthaqds5RSls6ry6hk6ny6wCgHua2K6vua+K6laQRK6sya+i6iyazEq6c61NagPDLxK+BMCKqvlbERSRzK9LSskqzE6qza6vKyzKDS0IswZJAaY6zQ63zavg6s06zA67daiEZezMIhQdq6ho6yI6hk6sQ6h4Ac867galq6ys+bcjIa6oY6xo6/4akS6qeyia6nSaqa625UFwlXI6u0699qoI6sY64wKmAskds2yWLo6io6go6na6/0qva6ga6xGgDa6ha65o6pUq5a65Zas66k6oBuWDq64w61tano6rw6mMq+6660gjOWJ666y6pa6u86nUamEahKa9Oq+5a0SbYJgwHYK8Iehar2ymiqvS6xuyw73czqoy6qDUVhavaq0G6ukc0Jqyy6jnJQjakbamKapuqnGqgK6py6zs6ly6xQq+ky5G6jUc8K69G6t9qrK67G65lqxy66yq6o6xZqxuawfQYHSFXDWa68rSjK64S63uaqIqvy612a42q1BoPG6oK605q+m64m6rbqg3Szy6iK6iIaim6pFqnG67m6laQXm61vanVqgW63xoNTC/dalm60W6ura/5q6K6s1q6m6hK62m60y6om6hW68FXaOy1m64nayaKrua7K6yHahWqqW692awq61naws6gG64s6huK87SjS6o3a4W/X/DJac6xq8vS69q9Dq7i6v86uva526ovqoeqE464ba+Ja5na5y6/c677q0umLQ4cjwSdqAO6hS6zG6js6txakc66rKkLS4G63LytAYB0gok6oyKpyap9ao8yr26ky6kI62NBR6ioi6mO6oO6uO6z2ayna1Ny/O6/6iwu61W6uJapzaku665ahO6+4ql863/K2ZcyC8TC6j4q7C6tBquKquA6uNq8WsitMai64i6jLK0i63q6mPy4Zcvu6qu62Y6xS6uu6uKa4q6wG65NS/xSlC6sLaotrE3ajKan4WL864NKiByuGani6sXqps6hvazva+uqicazBy8Fak/ajJy/0an3ajNKtaasZS+dS3k6vwK7aKyhylFa6Ma7XMEU6zFa1ZSwla6IK3ma3Favca1+6/xysB5BU61PasA89Pal6KgsakRynM0Wla3Pa0aU+5Sisaz1oXU60dK2sa39SoGahsa78amdK5sanq6rs6pLape63e6yaajdK5xa2TK/ba0g63ratwwGWahtqsaK/e6h06gYKvval062cat06rXUD06xlSr06jaIMfav069VazxygAkIM65+wEM6vVauPahfao1ayM6k1a0WKyVSi1a+ma5hua1a28aj3BZM61majD6A/a9M6o/at8anM69tqWR68/arlav8a7XairKlOqm/apIywNa+/asCa3LKl3I5/auWa1/amCa7/a6jKz/aox6wx63fEOjKhjKhi6nE69Xq8LgQHYTGysA66Yqs3azDwC3atJSik6+9q0jcWx60GymGa0caq66+06pk6w+6lk67VStk6xDKoZSzk6i+6kMagPahFavxbbaanaK++6sPax+6/YhUU6l+6xPat+6s6aqtK6U64la66a4la3+61IKilawRy1U64B6h9SryzMB6u5S19SplaqB64vamB6n9SpRy506jlaqva/M6oe61B64Kamx65BjLnEG06rB6tYaz+a3/qz4avkilp6pejPe649K0h64olJGaivasjS0YK9064fahmK5lSn06tca9lSph6t9Komanxy9h6g8azh68M67h67YK3h6lfa/h69fawR6+r5YR67fayXWKDKlM6/fatM6zQiDM6qFarM61DKnma7WKkGa71apR60jartam26tR6v4Ko/SoNarsbDHjNYoLejJejOCbAx66Nama4KjKv562Nasx65Ca+jKibaljqtja23Kjja2XoG+jK5UB9a9u6szazu6gxa726p+a2UFaF6vs6n9agSALq6my6+Xa/la0O672qiJ8zWstF6iKa53a6TarF65R6+Rag/K0F6huKgAARTKut10t74HhKtUatiUuRj3eCli2rHonhusZKq3upsiqwxBO1g6CqEyG7GtvOoaeoJusp8ua72dKAO/GyMsujBbWpcWqu2tiOrLurZ8tfhAZepf8olet3Or+uoUWr12sTuvGWr06v0qvzmG5H1heoratrOufWvrOqReuWWpbPPN/OWGv7OswY0HOsnur3OsO2u7Oq1eu2MLNevReoZ8sWusHut9Wv+uspetC0p9irxOtTcoPkq95zacuQ6szuv1euzurBOv2OoEOukAvrav7uqOutoupQeqFeuk8u0Ap7avHutGurOOroupUuttusfOr8UqAOvz0ragvqqGsyozuvSwlUSoqqpUgEjQFXOtF2v+2toMqzepKgtGisQqWVeuHqs5uvZuu6auQcpvOvxutxerzmoFuoKYmEQCnrn7qsXqrfauXqtsuuFavDmocusweq3qsaGsxatNMqzeoYmH+6qMqoHqoiGp7esZatpqv8uotusber5upHetoMq7gjdaArevkqqneuruv78prerneq5uurmtbqqHerwepZqpCuruoHujPHeoDms3euGGpnetDmtretyuvXqs7UsXetluuPevpus+BjXetuYQveq7eunerK8spuvnev3eonqsPeq/muXeoUMtfevbepwOE7erZIET8uvet8ut3errevUqoPeux0qferpuuJqtBurfevYfkresvetKGqg+tNutvev7erius6CoJbCturiOtcut1utfAKkQA7eoXqog+u7eu/eoluqpusHeoQ+uHerluuQ+rbev4CuSFHA+pLqqveuo+pyutw+ryuvw+snqujmobuo8WrV6q9eu/iqul1ZsvseuAco4uuISuF2pzupDesVGsCr2vywniq3ipCWqNuu2WsUuq12vueqEWubeu4GuqstZWHB/Vqmvkuq3euuusj0vU+rAusV6ptuvdeqtquR2vgPF/w0dqsqWq2OqYWqx2sNetzupSWvrKHT6oLMokWrpGrU2qTeujeq0+uCmsGEChBC7w2POpnBU8+tKGrGut2Wo0+pUepnurtusuSuhOpSmuyyFsevhSqrOtcOxjm2MCETiveSoXAE+Ssaurz6sFytUMFnZn5SvN6rZStUGulepDuptes0Gty+v9aFGIGSOvtwkDirgupnmuN6oYIExSuZuuxUuq+s7KlEOtwesA+tOGsUdMa+oFSpq+qK+s6etwWpc+r9UmZSp6+ta+tGuva+q6esZ6q2EEJE0BSoK+sRStq+qY2qi+rTeodssduvCUuA2umZ15GsqWv/KrLytaNFs5BYWqNevkmv+bJtKD76oDyqwquwepJGqHOp8+tK+r8+oEP3J0wuGolhFO+qkWtU+tjuuTevM+ug2rBeqbupxit5/g8KwhupayqwuvherrOtosv2+py+q++o97O/WqJetC+u8+sFet8+uNeqpGpAIoTerZuvyOqjeuUute+v/2tjmo1euoWsFutLIrR2tL0qhuqpwETithuvs+GLeqA+pBur1uqx+tJut4qQxuuLuu0Kq4+qh2otusCutLuuCuvluo+erSuvJ+tjYET8vFupp+vNur/estuu1uspapCusFuq64F2SpFurJurFupNup/er3evNap5uppurmGuJ+quEgF+pjw1Z+vA4HZ+rF+po+t/esl+uluul+qXesY+pI+uB0kbIsV+p4quGGo5+rNurHqrp+pluoY+ufeuQ+r1uuM13SupVusN+pV+s5+pN+u5+vp+vrusW+rUuqKSo++oIMWD6q4o2x+uAcrImA6fRQfTW8vi4HkfC+ZBF2uxOu9iti+tTWs+BxXgCi8B9+teWqqWrDip2OqkKGt2rXOqwOpsQ23KpIVGjuvFWvO+qtesu+sJquk8rT+sQXKvKsz+oeOprur82tdetVesQuou0qZAHV6rBEPv1G42sZesLUpQ2pdqrBsrzWoN6pk+u7urIGtr+qo5z9qqbWto2qLutrus02uxetc2uh+vkmq7+rMjkbWtgS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urAHLBuCptSpvjBpH9CTBpTBp/BuQup1BtspoeKsghtLBtzBvrBuXMvXBrAhuLBsS+CXBvOBIrBonBqzBpZBtYyrrBprBsbBqfBGbBtohqspuXMvbBtXBq7Bp1BqOppC2v7BsrBqcwJHBuXMrHBqqpqjBuXMuahunBq6prnBs/BrC0qYuunBuXBv26FOpqZRvgbkoMrC0q3BtOpuipskhsHBu/BoKpvepuPBoahseprKptQQF+psvBt+ppvBtBptfBo8hqspqfBrlykfBtpBtqhrKstohsfBr/BoeppkMu9QGHBqIhvAhoLBquFHAhpYhqsppUWvLBpJpvghocQE5BuW+oyhvNBu0iufBo6prghuiptqhqSmuHBs5pstBpJppIhuhgE5BoohoyhoJpvIhplBrohuohrjtnd0WYhsghuRpsAOp1BuhpuIhu4htXBs76uHBvahqjBrqcrRBpFpuC2pyhohpqjBvEhrsk1XBukhvZBrVprFMtVBrZppkMqUhrROoshuuSrldD0hvYhpDACchp0hushv0hpI6CchtxRpMhvKhoEJvMhqchqshqchtshq0hsCUschoxBpTUpchsNpvchuSpp/Bugavyht8hqjBv8hu2yvChrMyuLNBPyvHOsChoShpjpotppihrRBrihoJBtrJF9BuShsghpJpvSht0pvNpqCqse2uSpvTpr8UvyhsMhqKhpMpt8UtxBucZFMhsqhvshpqhsUhvqhsUhuahsGpqjBrjmvLBpNpr8Us6hu00riK1nMqcUoeBtJAHgACWBqEACZgCcUviio6UvgAHNQHrUtOOwIQEJAHNQFcICSAD3QCAAAAA=="))
///////////////////////////////////////////////

///////////////////////////////////////////////
/* Utility functions */

var storagePrefix = 'KiCad_HTML_BOM__' + pcbdata.metadata.title + '__' +
pcbdata.metadata.revision + '__#';
var storage;

function initStorage(key) {
try {
window.localStorage.getItem("blank");
storage = window.localStorage;
} catch (e) {
// localStorage not available
}
if (!storage) {
try {
window.sessionStorage.getItem("blank");
storage = window.sessionStorage;
} catch (e) {
// sessionStorage also not available
}
}
}

function readStorage(key) {
if (storage) {
return storage.getItem(storagePrefix + key);
} else {
return null;
}
}

function writeStorage(key, value) {
if (storage) {
storage.setItem(storagePrefix + key, value);
}
}

function fancyDblClickHandler(el, onsingle, ondouble) {
return function() {
if (el.getAttribute("data-dblclick") == null) {
el.setAttribute("data-dblclick", 1);
setTimeout(function() {
if (el.getAttribute("data-dblclick") == 1) {
onsingle();
}
el.removeAttribute("data-dblclick");
}, 200);
} else {
el.removeAttribute("data-dblclick");
ondouble();
}
}
}

function smoothScrollToRow(rowid) {
document.getElementById(rowid).scrollIntoView({
behavior: "smooth",
block: "center",
inline: "nearest"
});
}

function focusInputField(input) {
input.scrollIntoView(false);
input.focus();
input.select();
}

function saveBomTable(output) {
var text = '';
for (var node of bomhead.childNodes[0].childNodes) {
if (node.firstChild) {
text += (output == 'csv' ? `"${node.firstChild.nodeValue}"` : node.firstChild.nodeValue);
}
if (node != bomhead.childNodes[0].lastChild) {
text += (output == 'csv' ? ',' : '\t');
}
}
text += '\n';
for (var row of bombody.childNodes) {
for (var cell of row.childNodes) {
let val = '';
for (var node of cell.childNodes) {
if (node.nodeName == "INPUT") {
if (node.checked) {
val += '✓';
}
} else if (node.nodeName == "MARK") {
val += node.firstChild.nodeValue;
} else {
val += node.nodeValue;
}
}
if (output == 'csv') {
val = val.replace(/\"/g, '\"\"'); // pair of double-quote characters
if (isNumeric(val)) {
val = +val;                     // use number
} else {
val = `"${val}"`;               // enclosed within double-quote
}
}
text += val;
if (cell != row.lastChild) {
text += (output == 'csv' ? ',' : '\t');
}
}
text += '\n';
}

if (output != 'clipboard') {
// To file: csv or txt
var blob = new Blob([text], {
type: `text/${output}`
});
saveFile(`${pcbdata.metadata.title}.${output}`, blob);
} else {
// To clipboard
var textArea = document.createElement("textarea");
textArea.classList.add('clipboard-temp');
textArea.value = text;

    document.body.appendChild(textArea);
    textArea.focus();
    textArea.select();

    try {
      if (document.execCommand('copy')) {
        console.log('Bom copied to clipboard.');
      }
    } catch (err) {
      console.log('Can not copy to clipboard.');
    }

    document.body.removeChild(textArea);
}
}

function isNumeric(str) {
/* https://stackoverflow.com/a/175787 */
return (typeof str != "string" ? false : !isNaN(str) && !isNaN(parseFloat(str)));
}

function removeGutterNode(node) {
for (var i = 0; i < node.childNodes.length; i++) {
if (node.childNodes[i].classList &&
node.childNodes[i].classList.contains("gutter")) {
node.removeChild(node.childNodes[i]);
break;
}
}
}

function cleanGutters() {
removeGutterNode(document.getElementById("bot"));
removeGutterNode(document.getElementById("canvasdiv"));
}

var units = {
prefixes: {
giga: ["G", "g", "giga", "Giga", "GIGA"],
mega: ["M", "mega", "Mega", "MEGA"],
kilo: ["K", "k", "kilo", "Kilo", "KILO"],
milli: ["m", "milli", "Milli", "MILLI"],
micro: ["U", "u", "micro", "Micro", "MICRO", "μ", "µ"], // different utf8 μ
nano: ["N", "n", "nano", "Nano", "NANO"],
pico: ["P", "p", "pico", "Pico", "PICO"],
},
unitsShort: ["R", "r", "Ω", "F", "f", "H", "h"],
unitsLong: [
"OHM", "Ohm", "ohm", "ohms",
"FARAD", "Farad", "farad",
"HENRY", "Henry", "henry"
],
getMultiplier: function(s) {
if (this.prefixes.giga.includes(s)) return 1e9;
if (this.prefixes.mega.includes(s)) return 1e6;
if (this.prefixes.kilo.includes(s)) return 1e3;
if (this.prefixes.milli.includes(s)) return 1e-3;
if (this.prefixes.micro.includes(s)) return 1e-6;
if (this.prefixes.nano.includes(s)) return 1e-9;
if (this.prefixes.pico.includes(s)) return 1e-12;
return 1;
},
valueRegex: null,
}

function initUtils() {
var allPrefixes = units.prefixes.giga
.concat(units.prefixes.mega)
.concat(units.prefixes.kilo)
.concat(units.prefixes.milli)
.concat(units.prefixes.micro)
.concat(units.prefixes.nano)
.concat(units.prefixes.pico);
var allUnits = units.unitsShort.concat(units.unitsLong);
units.valueRegex = new RegExp("^([0-9\.]+)" +
"\\s*(" + allPrefixes.join("|") + ")?" +
"(" + allUnits.join("|") + ")?" +
"(\\b.*)?$", "");
units.valueAltRegex = new RegExp("^([0-9]*)" +
"(" + units.unitsShort.join("|") + ")?" +
"([GgMmKkUuNnPp])?" +
"([0-9]*)" +
"(\\b.*)?$", "");
if (config.fields.includes("Value")) {
var index = config.fields.indexOf("Value");
pcbdata.bom["parsedValues"] = {};
for (var id in pcbdata.bom.fields) {
pcbdata.bom.parsedValues[id] = parseValue(pcbdata.bom.fields[id][index])
}
}
}

function parseValue(val, ref) {
var inferUnit = (unit, ref) => {
if (unit) {
unit = unit.toLowerCase();
if (unit == 'Ω' || unit == "ohm" || unit == "ohms") {
unit = 'r';
}
unit = unit[0];
} else {
ref = /^([a-z]+)\d+$/i.exec(ref);
if (ref) {
ref = ref[1].toLowerCase();
if (ref == "c") unit = 'f';
else if (ref == "l") unit = 'h';
else if (ref == "r" || ref == "rv") unit = 'r';
else unit = null;
}
}
return unit;
};
val = val.replace(/,/g, "");
var match = units.valueRegex.exec(val);
var unit;
if (match) {
val = parseFloat(match[1]);
if (match[2]) {
val = val * units.getMultiplier(match[2]);
}
unit = inferUnit(match[3], ref);
if (!unit) return null;
else return {
val: val,
unit: unit,
extra: match[4],
}
}
match = units.valueAltRegex.exec(val);
if (match && (match[1] || match[4])) {
val = parseFloat(match[1] + "." + match[4]);
if (match[3]) {
val = val * units.getMultiplier(match[3]);
}
unit = inferUnit(match[2], ref);
if (!unit) return null;
else return {
val: val,
unit: unit,
extra: match[5],
}
}
return null;
}

function valueCompare(a, b, stra, strb) {
if (a === null && b === null) {
// Failed to parse both values, compare them as strings.
if (stra != strb) return stra > strb ? 1 : -1;
else return 0;
} else if (a === null) {
return 1;
} else if (b === null) {
return -1;
} else {
if (a.unit != b.unit) return a.unit > b.unit ? 1 : -1;
else if (a.val != b.val) return a.val > b.val ? 1 : -1;
else if (a.extra != b.extra) return a.extra > b.extra ? 1 : -1;
else return 0;
}
}

function validateSaveImgDimension(element) {
var valid = false;
var intValue = 0;
if (/^[1-9]\d*$/.test(element.value)) {
intValue = parseInt(element.value);
if (intValue <= 16000) {
valid = true;
}
}
if (valid) {
element.classList.remove("invalid");
} else {
element.classList.add("invalid");
}
return intValue;
}

function saveImage(layer) {
var width = validateSaveImgDimension(document.getElementById("render-save-width"));
var height = validateSaveImgDimension(document.getElementById("render-save-height"));
var bgcolor = null;
if (!document.getElementById("render-save-transparent").checked) {
var style = getComputedStyle(topmostdiv);
bgcolor = style.getPropertyValue("background-color");
}
if (!width || !height) return;

// Prepare image
var canvas = document.createElement("canvas");
var layerdict = {
transform: {
x: 0,
y: 0,
s: 1,
panx: 0,
pany: 0,
zoom: 1,
},
bg: canvas,
fab: canvas,
silk: canvas,
highlight: canvas,
layer: layer,
}
// Do the rendering
recalcLayerScale(layerdict, width, height);
prepareLayer(layerdict);
clearCanvas(canvas, bgcolor);
drawBackground(layerdict, false);
drawHighlightsOnLayer(layerdict, false);

// Save image
var imgdata = canvas.toDataURL("image/png");

var filename = pcbdata.metadata.title;
if (pcbdata.metadata.revision) {
filename += `.${pcbdata.metadata.revision}`;
}
filename += `.${layer}.png`;
saveFile(filename, dataURLtoBlob(imgdata));
}

function saveSettings() {
var data = {
type: "InteractiveHtmlBom settings",
version: 1,
pcbmetadata: pcbdata.metadata,
settings: settings,
}
var blob = new Blob([JSON.stringify(data, null, 4)], {
type: "application/json"
});
saveFile(`${pcbdata.metadata.title}.settings.json`, blob);
}

function loadSettings() {
var input = document.createElement("input");
input.type = "file";
input.accept = ".settings.json";
input.onchange = function(e) {
var file = e.target.files[0];
var reader = new FileReader();
reader.onload = readerEvent => {
var content = readerEvent.target.result;
var newSettings;
try {
newSettings = JSON.parse(content);
} catch (e) {
alert("Selected file is not InteractiveHtmlBom settings file.");
return;
}
if (newSettings.type != "InteractiveHtmlBom settings") {
alert("Selected file is not InteractiveHtmlBom settings file.");
return;
}
var metadataMatches = newSettings.hasOwnProperty("pcbmetadata");
if (metadataMatches) {
for (var k in pcbdata.metadata) {
if (!newSettings.pcbmetadata.hasOwnProperty(k) || newSettings.pcbmetadata[k] != pcbdata.metadata[k]) {
metadataMatches = false;
}
}
}
if (!metadataMatches) {
var currentMetadata = JSON.stringify(pcbdata.metadata, null, 4);
var fileMetadata = JSON.stringify(newSettings.pcbmetadata, null, 4);
if (!confirm(
`Settins file metadata does not match current metadata.\n\n` +
`Page metadata:\n${currentMetadata}\n\n` +
`Settings file metadata:\n${fileMetadata}\n\n` +
`Press OK if you would like to import settings anyway.`)) {
return;
}
}
overwriteSettings(newSettings.settings);
}
reader.readAsText(file, 'UTF-8');
}
input.click();
}

function overwriteSettings(newSettings) {
initDone = false;
Object.assign(settings, newSettings);
writeStorage("bomlayout", settings.bomlayout);
writeStorage("bommode", settings.bommode);
writeStorage("canvaslayout", settings.canvaslayout);
writeStorage("bomCheckboxes", settings.checkboxes.join(","));
document.getElementById("bomCheckboxes").value = settings.checkboxes.join(",");
for (var checkbox of settings.checkboxes) {
writeStorage("checkbox_" + checkbox, settings.checkboxStoredRefs[checkbox]);
}
writeStorage("markWhenChecked", settings.markWhenChecked);
padsVisible(settings.renderPads);
document.getElementById("padsCheckbox").checked = settings.renderPads;
fabricationVisible(settings.renderFabrication);
document.getElementById("fabricationCheckbox").checked = settings.renderFabrication;
silkscreenVisible(settings.renderSilkscreen);
document.getElementById("silkscreenCheckbox").checked = settings.renderSilkscreen;
referencesVisible(settings.renderReferences);
document.getElementById("referencesCheckbox").checked = settings.renderReferences;
valuesVisible(settings.renderValues);
document.getElementById("valuesCheckbox").checked = settings.renderValues;
tracksVisible(settings.renderTracks);
document.getElementById("tracksCheckbox").checked = settings.renderTracks;
zonesVisible(settings.renderZones);
document.getElementById("zonesCheckbox").checked = settings.renderZones;
dnpOutline(settings.renderDnpOutline);
document.getElementById("dnpOutlineCheckbox").checked = settings.renderDnpOutline;
setRedrawOnDrag(settings.redrawOnDrag);
document.getElementById("dragCheckbox").checked = settings.redrawOnDrag;
setDarkMode(settings.darkMode);
document.getElementById("darkmodeCheckbox").checked = settings.darkMode;
setHighlightPin1(settings.highlightpin1);
document.getElementById("highlightpin1Checkbox").checked = settings.highlightpin1;
showFootprints(settings.show_footprints);
writeStorage("boardRotation", settings.boardRotation);
document.getElementById("boardRotation").value = settings.boardRotation / 5;
document.getElementById("rotationDegree").textContent = settings.boardRotation;
initDone = true;
prepCheckboxes();
changeBomLayout(settings.bomlayout);
}

function saveFile(filename, blob) {
var link = document.createElement("a");
var objurl = URL.createObjectURL(blob);
link.download = filename;
link.href = objurl;
link.click();
}

function dataURLtoBlob(dataurl) {
var arr = dataurl.split(','),
mime = arr[0].match(/:(.*?);/)[1],
bstr = atob(arr[1]),
n = bstr.length,
u8arr = new Uint8Array(n);
while (n--) {
u8arr[n] = bstr.charCodeAt(n);
}
return new Blob([u8arr], {
type: mime
});
}

var settings = {
canvaslayout: "default",
bomlayout: "default",
bommode: "grouped",
checkboxes: [],
checkboxStoredRefs: {},
darkMode: false,
highlightpin1: false,
redrawOnDrag: true,
boardRotation: 0,
renderPads: true,
renderReferences: true,
renderValues: true,
renderSilkscreen: true,
renderFabrication: true,
renderDnpOutline: false,
renderTracks: true,
renderZones: true,
columnOrder: [],
hiddenColumns: [],
}

function initDefaults() {
settings.bomlayout = readStorage("bomlayout");
if (settings.bomlayout === null) {
settings.bomlayout = config.bom_view;
}
if (!['bom-only', 'left-right', 'top-bottom'].includes(settings.bomlayout)) {
settings.bomlayout = config.bom_view;
}
settings.bommode = readStorage("bommode");
if (settings.bommode === null) {
settings.bommode = "grouped";
}
if (!["grouped", "ungrouped", "netlist"].includes(settings.bommode)) {
settings.bommode = "grouped";
}
settings.canvaslayout = readStorage("canvaslayout");
if (settings.canvaslayout === null) {
settings.canvaslayout = config.layer_view;
}
var bomCheckboxes = readStorage("bomCheckboxes");
if (bomCheckboxes === null) {
bomCheckboxes = config.checkboxes;
}
settings.checkboxes = bomCheckboxes.split(",").filter((e) => e);
document.getElementById("bomCheckboxes").value = bomCheckboxes;

settings.markWhenChecked = readStorage("markWhenChecked") || "";
populateMarkWhenCheckedOptions();

function initBooleanSetting(storageString, def, elementId, func) {
var b = readStorage(storageString);
if (b === null) {
b = def;
} else {
b = (b == "true");
}
document.getElementById(elementId).checked = b;
func(b);
}

initBooleanSetting("padsVisible", config.show_pads, "padsCheckbox", padsVisible);
initBooleanSetting("fabricationVisible", config.show_fabrication, "fabricationCheckbox", fabricationVisible);
initBooleanSetting("silkscreenVisible", config.show_silkscreen, "silkscreenCheckbox", silkscreenVisible);
initBooleanSetting("referencesVisible", true, "referencesCheckbox", referencesVisible);
initBooleanSetting("valuesVisible", true, "valuesCheckbox", valuesVisible);
if ("tracks" in pcbdata) {
initBooleanSetting("tracksVisible", true, "tracksCheckbox", tracksVisible);
initBooleanSetting("zonesVisible", true, "zonesCheckbox", zonesVisible);
} else {
document.getElementById("tracksAndZonesCheckboxes").style.display = "none";
tracksVisible(false);
zonesVisible(false);
}
initBooleanSetting("dnpOutline", false, "dnpOutlineCheckbox", dnpOutline);
initBooleanSetting("redrawOnDrag", config.redraw_on_drag, "dragCheckbox", setRedrawOnDrag);
initBooleanSetting("darkmode", config.dark_mode, "darkmodeCheckbox", setDarkMode);
initBooleanSetting("highlightpin1", config.highlight_pin1, "highlightpin1Checkbox", setHighlightPin1);

var fields = ["checkboxes", "References"].concat(config.fields).concat(["Quantity"]);
var hcols = JSON.parse(readStorage("hiddenColumns"));
if (hcols === null) {
hcols = [];
}
settings.hiddenColumns = hcols.filter(e => fields.includes(e));

var cord = JSON.parse(readStorage("columnOrder"));
if (cord === null) {
cord = fields;
} else {
cord = cord.filter(e => fields.includes(e));
if (cord.length != fields.length)
cord = fields;
}
settings.columnOrder = cord;

settings.boardRotation = readStorage("boardRotation");
if (settings.boardRotation === null) {
settings.boardRotation = config.board_rotation * 5;
} else {
settings.boardRotation = parseInt(settings.boardRotation);
}
document.getElementById("boardRotation").value = settings.boardRotation / 5;
document.getElementById("rotationDegree").textContent = settings.boardRotation;
}

// Helper classes for user js callbacks.

const IBOM_EVENT_TYPES = {
ALL: "all",
HIGHLIGHT_EVENT: "highlightEvent",
CHECKBOX_CHANGE_EVENT: "checkboxChangeEvent",
BOM_BODY_CHANGE_EVENT: "bomBodyChangeEvent",
}

const EventHandler = {
callbacks: {},
init: function() {
for (eventType of Object.values(IBOM_EVENT_TYPES))
this.callbacks[eventType] = [];
},
registerCallback: function(eventType, callback) {
this.callbacks[eventType].push(callback);
},
emitEvent: function(eventType, eventArgs) {
event = {
eventType: eventType,
args: eventArgs,
}
var callback;
for (callback of this.callbacks[eventType])
callback(event);
for (callback of this.callbacks[IBOM_EVENT_TYPES.ALL])
callback(event);
}
}
EventHandler.init();

///////////////////////////////////////////////

///////////////////////////////////////////////
/* PCB rendering code */

var emptyContext2d = document.createElement("canvas").getContext("2d");

function deg2rad(deg) {
return deg * Math.PI / 180;
}

function calcFontPoint(linepoint, text, offsetx, offsety, tilt) {
var point = [
linepoint[0] * text.width + offsetx,
linepoint[1] * text.height + offsety
];
// This approximates pcbnew behavior with how text tilts depending on horizontal justification
point[0] -= (linepoint[1] + 0.5 * (1 + text.justify[0])) * text.height * tilt;
return point;
}

function drawText(ctx, text, color) {
if ("ref" in text && !settings.renderReferences) return;
if ("val" in text && !settings.renderValues) return;
ctx.save();
ctx.fillStyle = color;
ctx.strokeStyle = color;
ctx.lineCap = "round";
ctx.lineJoin = "round";
ctx.lineWidth = text.thickness;
if ("svgpath" in text) {
ctx.stroke(new Path2D(text.svgpath));
ctx.restore();
return;
}
if ("polygons" in text) {
ctx.fill(getPolygonsPath(text));
ctx.restore();
return;
}
ctx.translate(...text.pos);
ctx.translate(text.thickness * 0.5, 0);
var angle = -text.angle;
if (text.attr.includes("mirrored")) {
ctx.scale(-1, 1);
angle = -angle;
}
var tilt = 0;
if (text.attr.includes("italic")) {
tilt = 0.125;
}
var interline = text.height * 1.5 + text.thickness;
var txt = text.text.split("\n");
// KiCad ignores last empty line.
if (txt[txt.length - 1] == '') txt.pop();
ctx.rotate(deg2rad(angle));
var offsety = (1 - text.justify[1]) / 2 * text.height; // One line offset
offsety -= (txt.length - 1) * (text.justify[1] + 1) / 2 * interline; // Multiline offset
for (var i in txt) {
var lineWidth = text.thickness + interline / 2 * tilt;
for (var j = 0; j < txt[i].length; j++) {
if (txt[i][j] == '\t') {
var fourSpaces = 4 * pcbdata.font_data[' '].w * text.width;
lineWidth += fourSpaces - lineWidth % fourSpaces;
} else {
if (txt[i][j] == '~') {
j++;
if (j == txt[i].length)
break;
}
lineWidth += pcbdata.font_data[txt[i][j]].w * text.width;
}
}
var offsetx = -lineWidth * (text.justify[0] + 1) / 2;
var inOverbar = false;
for (var j = 0; j < txt[i].length; j++) {
if (txt[i][j] == '\t') {
var fourSpaces = 4 * pcbdata.font_data[' '].w * text.width;
offsetx += fourSpaces - offsetx % fourSpaces;
continue;
} else if (txt[i][j] == '~') {
j++;
if (j == txt[i].length)
break;
if (txt[i][j] != '~') {
inOverbar = !inOverbar;
}
}
var glyph = pcbdata.font_data[txt[i][j]];
if (inOverbar) {
var overbarStart = [offsetx, -text.height * 1.4 + offsety];
var overbarEnd = [offsetx + text.width * glyph.w, overbarStart[1]];

        if (!lastHadOverbar) {
          overbarStart[0] += text.height * 1.4 * tilt;
          lastHadOverbar = true;
        }
        ctx.beginPath();
        ctx.moveTo(...overbarStart);
        ctx.lineTo(...overbarEnd);
        ctx.stroke();
      } else {
        lastHadOverbar = false;
      }
      for (var line of glyph.l) {
        ctx.beginPath();
        ctx.moveTo(...calcFontPoint(line[0], text, offsetx, offsety, tilt));
        for (var k = 1; k < line.length; k++) {
          ctx.lineTo(...calcFontPoint(line[k], text, offsetx, offsety, tilt));
        }
        ctx.stroke();
      }
      offsetx += glyph.w * text.width;
    }
    offsety += interline;
}
ctx.restore();
}

function drawedge(ctx, scalefactor, edge, color) {
ctx.strokeStyle = color;
ctx.fillStyle = color;
ctx.lineWidth = Math.max(1 / scalefactor, edge.width);
ctx.lineCap = "round";
ctx.lineJoin = "round";
if ("svgpath" in edge) {
ctx.stroke(new Path2D(edge.svgpath));
} else {
ctx.beginPath();
if (edge.type == "segment") {
ctx.moveTo(...edge.start);
ctx.lineTo(...edge.end);
}
if (edge.type == "rect") {
ctx.moveTo(...edge.start);
ctx.lineTo(edge.start[0], edge.end[1]);
ctx.lineTo(...edge.end);
ctx.lineTo(edge.end[0], edge.start[1]);
ctx.lineTo(...edge.start);
}
if (edge.type == "arc") {
ctx.arc(
...edge.start,
edge.radius,
deg2rad(edge.startangle),
deg2rad(edge.endangle));
}
if (edge.type == "circle") {
ctx.arc(
...edge.start,
edge.radius,
0, 2 * Math.PI);
ctx.closePath();
}
if (edge.type == "curve") {
ctx.moveTo(...edge.start);
ctx.bezierCurveTo(...edge.cpa, ...edge.cpb, ...edge.end);
}
if("filled" in edge && edge.filled)
ctx.fill();
else
ctx.stroke();
}
}

function getChamferedRectPath(size, radius, chamfpos, chamfratio) {
// chamfpos is a bitmask, left = 1, right = 2, bottom left = 4, bottom right = 8
var path = new Path2D();
var width = size[0];
var height = size[1];
var x = width * -0.5;
var y = height * -0.5;
var chamfOffset = Math.min(width, height) * chamfratio;
path.moveTo(x, 0);
if (chamfpos & 4) {
path.lineTo(x, y + height - chamfOffset);
path.lineTo(x + chamfOffset, y + height);
path.lineTo(0, y + height);
} else {
path.arcTo(x, y + height, x + width, y + height, radius);
}
if (chamfpos & 8) {
path.lineTo(x + width - chamfOffset, y + height);
path.lineTo(x + width, y + height - chamfOffset);
path.lineTo(x + width, 0);
} else {
path.arcTo(x + width, y + height, x + width, y, radius);
}
if (chamfpos & 2) {
path.lineTo(x + width, y + chamfOffset);
path.lineTo(x + width - chamfOffset, y);
path.lineTo(0, y);
} else {
path.arcTo(x + width, y, x, y, radius);
}
if (chamfpos & 1) {
path.lineTo(x + chamfOffset, y);
path.lineTo(x, y + chamfOffset);
path.lineTo(x, 0);
} else {
path.arcTo(x, y, x, y + height, radius);
}
path.closePath();
return path;
}

function getOblongPath(size) {
return getChamferedRectPath(size, Math.min(size[0], size[1]) / 2, 0, 0);
}

function getPolygonsPath(shape) {
if (shape.path2d) {
return shape.path2d;
}
if ("svgpath" in shape) {
shape.path2d = new Path2D(shape.svgpath);
} else {
var path = new Path2D();
for (var polygon of shape.polygons) {
path.moveTo(...polygon[0]);
for (var i = 1; i < polygon.length; i++) {
path.lineTo(...polygon[i]);
}
path.closePath();
}
shape.path2d = path;
}
return shape.path2d;
}

function drawPolygonShape(ctx, scalefactor, shape, color) {
ctx.save();
if (!("svgpath" in shape)) {
ctx.translate(...shape.pos);
ctx.rotate(deg2rad(-shape.angle));
}
if("filled" in shape && !shape.filled) {
ctx.strokeStyle = color;
ctx.lineWidth = Math.max(1 / scalefactor, shape.width);
ctx.lineCap = "round";
ctx.lineJoin = "round";
ctx.stroke(getPolygonsPath(shape));
} else {
ctx.fillStyle = color;
ctx.fill(getPolygonsPath(shape));
}
ctx.restore();
}

function drawDrawing(ctx, scalefactor, drawing, color) {
if (["segment", "arc", "circle", "curve", "rect"].includes(drawing.type)) {
drawedge(ctx, scalefactor, drawing, color);
} else if (drawing.type == "polygon") {
drawPolygonShape(ctx, scalefactor, drawing, color);
} else {
drawText(ctx, drawing, color);
}
}

function getCirclePath(radius) {
var path = new Path2D();
path.arc(0, 0, radius, 0, 2 * Math.PI);
path.closePath();
return path;
}

function getCachedPadPath(pad) {
if (!pad.path2d) {
// if path2d is not set, build one and cache it on pad object
if (pad.shape == "rect") {
pad.path2d = new Path2D();
pad.path2d.rect(...pad.size.map(c => -c * 0.5), ...pad.size);
} else if (pad.shape == "oval") {
pad.path2d = getOblongPath(pad.size);
} else if (pad.shape == "circle") {
pad.path2d = getCirclePath(pad.size[0] / 2);
} else if (pad.shape == "roundrect") {
pad.path2d = getChamferedRectPath(pad.size, pad.radius, 0, 0);
} else if (pad.shape == "chamfrect") {
pad.path2d = getChamferedRectPath(pad.size, pad.radius, pad.chamfpos, pad.chamfratio)
} else if (pad.shape == "custom") {
pad.path2d = getPolygonsPath(pad);
}
}
return pad.path2d;
}

function drawPad(ctx, pad, color, outline) {
ctx.save();
ctx.translate(...pad.pos);
ctx.rotate(-deg2rad(pad.angle));
if (pad.offset) {
ctx.translate(...pad.offset);
}
ctx.fillStyle = color;
ctx.strokeStyle = color;
var path = getCachedPadPath(pad);
if (outline) {
ctx.stroke(path);
} else {
ctx.fill(path);
}
ctx.restore();
}

function drawPadHole(ctx, pad, padHoleColor) {
if (pad.type != "th") return;
ctx.save();
ctx.translate(...pad.pos);
ctx.rotate(-deg2rad(pad.angle));
ctx.fillStyle = padHoleColor;
if (pad.drillshape == "oblong") {
ctx.fill(getOblongPath(pad.drillsize));
} else {
ctx.fill(getCirclePath(pad.drillsize[0] / 2));
}
ctx.restore();
}

function drawFootprint(ctx, layer, scalefactor, footprint, colors, highlight, outline) {
if (highlight) {
// draw bounding box
if (footprint.layer == layer) {
ctx.save();
ctx.globalAlpha = 0.2;
ctx.translate(...footprint.bbox.pos);
ctx.rotate(deg2rad(-footprint.bbox.angle));
ctx.translate(...footprint.bbox.relpos);
ctx.fillStyle = colors.pad;
ctx.fillRect(0, 0, ...footprint.bbox.size);
ctx.globalAlpha = 1;
ctx.strokeStyle = colors.pad;
ctx.strokeRect(0, 0, ...footprint.bbox.size);
ctx.restore();
}
}
// draw drawings
for (var drawing of footprint.drawings) {
if (drawing.layer == layer) {
drawDrawing(ctx, scalefactor, drawing.drawing, colors.pad);
}
}
// draw pads
if (settings.renderPads) {
for (var pad of footprint.pads) {
if (pad.layers.includes(layer)) {
drawPad(ctx, pad, colors.pad, outline);
if (pad.pin1 && settings.highlightpin1) {
drawPad(ctx, pad, colors.outline, true);
}
}
}
for (var pad of footprint.pads) {
drawPadHole(ctx, pad, colors.padHole);
}
}
}

function drawEdgeCuts(canvas, scalefactor) {
var ctx = canvas.getContext("2d");
var edgecolor = getComputedStyle(topmostdiv).getPropertyValue('--pcb-edge-color');
for (var edge of pcbdata.edges) {
drawDrawing(ctx, scalefactor, edge, edgecolor);
}
}

function drawFootprints(canvas, layer, scalefactor, highlight) {
var ctx = canvas.getContext("2d");
ctx.lineWidth = 3 / scalefactor;
var style = getComputedStyle(topmostdiv);

var colors = {
pad: style.getPropertyValue('--pad-color'),
padHole: style.getPropertyValue('--pad-hole-color'),
outline: style.getPropertyValue('--pin1-outline-color'),
}

for (var i = 0; i < pcbdata.footprints.length; i++) {
var mod = pcbdata.footprints[i];
var outline = settings.renderDnpOutline && pcbdata.bom.skipped.includes(i);
var h = highlightedFootprints.includes(i);
var d = markedFootprints.has(i);
if (highlight) {
if(h && d) {
colors.pad = style.getPropertyValue('--pad-color-highlight-both');
colors.outline = style.getPropertyValue('--pin1-outline-color-highlight-both');
} else if (h) {
colors.pad = style.getPropertyValue('--pad-color-highlight');
colors.outline = style.getPropertyValue('--pin1-outline-color-highlight');
} else if (d) {
colors.pad = style.getPropertyValue('--pad-color-highlight-marked');
colors.outline = style.getPropertyValue('--pin1-outline-color-highlight-marked');
}
}
if( h || d || !highlight) {
drawFootprint(ctx, layer, scalefactor, mod, colors, highlight, outline);
}
}
}

function drawBgLayer(layername, canvas, layer, scalefactor, edgeColor, polygonColor, textColor) {
var ctx = canvas.getContext("2d");
for (var d of pcbdata.drawings[layername][layer]) {
if (["segment", "arc", "circle", "curve", "rect"].includes(d.type)) {
drawedge(ctx, scalefactor, d, edgeColor);
} else if (d.type == "polygon") {
drawPolygonShape(ctx, scalefactor, d, polygonColor);
} else {
drawText(ctx, d, textColor);
}
}
}

function drawTracks(canvas, layer, color, highlight) {
ctx = canvas.getContext("2d");
ctx.strokeStyle = color;
ctx.lineCap = "round";
for (var track of pcbdata.tracks[layer]) {
if (highlight && highlightedNet != track.net) continue;
ctx.lineWidth = track.width;
ctx.beginPath();
if ('radius' in track) {
ctx.arc(
...track.center,
track.radius,
deg2rad(track.startangle),
deg2rad(track.endangle));
} else {
ctx.moveTo(...track.start);
ctx.lineTo(...track.end);
}
ctx.stroke();
}
}

function drawZones(canvas, layer, color, highlight) {
ctx = canvas.getContext("2d");
ctx.strokeStyle = color;
ctx.fillStyle = color;
ctx.lineJoin = "round";
for (var zone of pcbdata.zones[layer]) {
if (!zone.path2d) {
zone.path2d = getPolygonsPath(zone);
}
if (highlight && highlightedNet != zone.net) continue;
ctx.fill(zone.path2d);
if (zone.width > 0) {
ctx.lineWidth = zone.width;
ctx.stroke(zone.path2d);
}
}
}

function clearCanvas(canvas, color = null) {
var ctx = canvas.getContext("2d");
ctx.save();
ctx.setTransform(1, 0, 0, 1, 0, 0);
if (color) {
ctx.fillStyle = color;
ctx.fillRect(0, 0, canvas.width, canvas.height);
} else {
if (!window.matchMedia("print").matches)
ctx.clearRect(0, 0, canvas.width, canvas.height);
}
ctx.restore();
}

function drawNets(canvas, layer, highlight) {
var style = getComputedStyle(topmostdiv);
if (settings.renderTracks) {
var trackColor = style.getPropertyValue(highlight ? '--track-color-highlight' : '--track-color');
drawTracks(canvas, layer, trackColor, highlight);
}
if (settings.renderZones) {
var zoneColor = style.getPropertyValue(highlight ? '--zone-color-highlight' : '--zone-color');
drawZones(canvas, layer, zoneColor, highlight);
}
if (highlight && settings.renderPads) {
var padColor = style.getPropertyValue('--pad-color-highlight');
var padHoleColor = style.getPropertyValue('--pad-hole-color');
var ctx = canvas.getContext("2d");
for (var footprint of pcbdata.footprints) {
// draw pads
var padDrawn = false;
for (var pad of footprint.pads) {
if (highlightedNet != pad.net) continue;
if (pad.layers.includes(layer)) {
drawPad(ctx, pad, padColor, false);
padDrawn = true;
}
}
if (padDrawn) {
// redraw all pad holes because some pads may overlap
for (var pad of footprint.pads) {
drawPadHole(ctx, pad, padHoleColor);
}
}
}
}
}

function drawHighlightsOnLayer(canvasdict, clear = true) {
if (clear) {
clearCanvas(canvasdict.highlight);
}
if (markedFootprints.size > 0 || highlightedFootprints.length > 0) {
drawFootprints(canvasdict.highlight, canvasdict.layer,
canvasdict.transform.s * canvasdict.transform.zoom, true);
}
if (highlightedNet !== null) {
drawNets(canvasdict.highlight, canvasdict.layer, true);
}
}

function drawHighlights() {
drawHighlightsOnLayer(allcanvas.front);
drawHighlightsOnLayer(allcanvas.back);
}

function drawBackground(canvasdict, clear = true) {
if (clear) {
clearCanvas(canvasdict.bg);
clearCanvas(canvasdict.fab);
clearCanvas(canvasdict.silk);
}

drawNets(canvasdict.bg, canvasdict.layer, false);
drawFootprints(canvasdict.bg, canvasdict.layer,
canvasdict.transform.s * canvasdict.transform.zoom, false);

drawEdgeCuts(canvasdict.bg, canvasdict.transform.s * canvasdict.transform.zoom);

var style = getComputedStyle(topmostdiv);
var edgeColor = style.getPropertyValue('--silkscreen-edge-color');
var polygonColor = style.getPropertyValue('--silkscreen-polygon-color');
var textColor = style.getPropertyValue('--silkscreen-text-color');
if (settings.renderSilkscreen) {
drawBgLayer(
"silkscreen", canvasdict.silk, canvasdict.layer,
canvasdict.transform.s * canvasdict.transform.zoom,
edgeColor, polygonColor, textColor);
}
edgeColor = style.getPropertyValue('--fabrication-edge-color');
polygonColor = style.getPropertyValue('--fabrication-polygon-color');
textColor = style.getPropertyValue('--fabrication-text-color');
if (settings.renderFabrication) {
drawBgLayer(
"fabrication", canvasdict.fab, canvasdict.layer,
canvasdict.transform.s * canvasdict.transform.zoom,
edgeColor, polygonColor, textColor);
}
}

function prepareCanvas(canvas, flip, transform) {
var ctx = canvas.getContext("2d");
ctx.setTransform(1, 0, 0, 1, 0, 0);
ctx.scale(transform.zoom, transform.zoom);
ctx.translate(transform.panx, transform.pany);
if (flip) {
ctx.scale(-1, 1);
}
ctx.translate(transform.x, transform.y);
ctx.rotate(deg2rad(settings.boardRotation));
ctx.scale(transform.s, transform.s);
}

function prepareLayer(canvasdict) {
var flip = (canvasdict.layer == "B");
for (var c of ["bg", "fab", "silk", "highlight"]) {
prepareCanvas(canvasdict[c], flip, canvasdict.transform);
}
}

function rotateVector(v, angle) {
angle = deg2rad(angle);
return [
v[0] * Math.cos(angle) - v[1] * Math.sin(angle),
v[0] * Math.sin(angle) + v[1] * Math.cos(angle)
];
}

function applyRotation(bbox) {
var corners = [
[bbox.minx, bbox.miny],
[bbox.minx, bbox.maxy],
[bbox.maxx, bbox.miny],
[bbox.maxx, bbox.maxy],
];
corners = corners.map((v) => rotateVector(v, settings.boardRotation));
return {
minx: corners.reduce((a, v) => Math.min(a, v[0]), Infinity),
miny: corners.reduce((a, v) => Math.min(a, v[1]), Infinity),
maxx: corners.reduce((a, v) => Math.max(a, v[0]), -Infinity),
maxy: corners.reduce((a, v) => Math.max(a, v[1]), -Infinity),
}
}

function recalcLayerScale(layerdict, width, height) {
var bbox = applyRotation(pcbdata.edges_bbox);
var scalefactor = 0.98 * Math.min(
width / (bbox.maxx - bbox.minx),
height / (bbox.maxy - bbox.miny)
);
if (scalefactor < 0.1) {
scalefactor = 1;
}
layerdict.transform.s = scalefactor;
var flip = (layerdict.layer == "B");
if (flip) {
layerdict.transform.x = -((bbox.maxx + bbox.minx) * scalefactor + width) * 0.5;
} else {
layerdict.transform.x = -((bbox.maxx + bbox.minx) * scalefactor - width) * 0.5;
}
layerdict.transform.y = -((bbox.maxy + bbox.miny) * scalefactor - height) * 0.5;
for (var c of ["bg", "fab", "silk", "highlight"]) {
canvas = layerdict[c];
canvas.width = width;
canvas.height = height;
canvas.style.width = (width / devicePixelRatio) + "px";
canvas.style.height = (height / devicePixelRatio) + "px";
}
}

function redrawCanvas(layerdict) {
prepareLayer(layerdict);
drawBackground(layerdict);
drawHighlightsOnLayer(layerdict);
}

function resizeCanvas(layerdict) {
var canvasdivid = {
"F": "frontcanvas",
"B": "backcanvas"
} [layerdict.layer];
var width = document.getElementById(canvasdivid).clientWidth * devicePixelRatio;
var height = document.getElementById(canvasdivid).clientHeight * devicePixelRatio;
recalcLayerScale(layerdict, width, height);
redrawCanvas(layerdict);
}

function resizeAll() {
resizeCanvas(allcanvas.front);
resizeCanvas(allcanvas.back);
}

function pointWithinDistanceToSegment(x, y, x1, y1, x2, y2, d) {
var A = x - x1;
var B = y - y1;
var C = x2 - x1;
var D = y2 - y1;

var dot = A * C + B * D;
var len_sq = C * C + D * D;
var dx, dy;
if (len_sq == 0) {
// start and end of the segment coincide
dx = x - x1;
dy = y - y1;
} else {
var param = dot / len_sq;
var xx, yy;
if (param < 0) {
xx = x1;
yy = y1;
} else if (param > 1) {
xx = x2;
yy = y2;
} else {
xx = x1 + param * C;
yy = y1 + param * D;
}
dx = x - xx;
dy = y - yy;
}
return dx * dx + dy * dy <= d * d;
}

function modulo(n, mod) {
return ((n % mod) + mod) % mod;
}

function pointWithinDistanceToArc(x, y, xc, yc, radius, startangle, endangle, d) {
var dx = x - xc;
var dy = y - yc;
var r_sq = dx * dx + dy * dy;
var rmin = Math.max(0, radius - d);
var rmax = radius + d;

if (r_sq < rmin * rmin || r_sq > rmax * rmax)
return false;

var angle1 = modulo(deg2rad(startangle), 2 * Math.PI);
var dx1 = xc + radius * Math.cos(angle1) - x;
var dy1 = yc + radius * Math.sin(angle1) - y;
if (dx1 * dx1 + dy1 * dy1 <= d * d)
return true;

var angle2 = modulo(deg2rad(endangle), 2 * Math.PI);
var dx2 = xc + radius * Math.cos(angle2) - x;
var dy2 = yc + radius * Math.sin(angle2) - y;
if (dx2 * dx2 + dy2 * dy2 <= d * d)
return true;

var angle = modulo(Math.atan2(dy, dx), 2 * Math.PI);
if (angle1 > angle2)
return (angle >= angle2 || angle <= angle1);
else
return (angle >= angle1 && angle <= angle2);
}

function pointWithinPad(x, y, pad) {
var v = [x - pad.pos[0], y - pad.pos[1]];
v = rotateVector(v, pad.angle);
if (pad.offset) {
v[0] -= pad.offset[0];
v[1] -= pad.offset[1];
}
return emptyContext2d.isPointInPath(getCachedPadPath(pad), ...v);
}

function netHitScan(layer, x, y) {
// Check track segments
if (settings.renderTracks && pcbdata.tracks) {
for (var track of pcbdata.tracks[layer]) {
if ('radius' in track) {
if (pointWithinDistanceToArc(x, y, ...track.center, track.radius, track.startangle, track.endangle, track.width / 2)) {
return track.net;
}
} else {
if (pointWithinDistanceToSegment(x, y, ...track.start, ...track.end, track.width / 2)) {
return track.net;
}
}
}
}
// Check pads
if (settings.renderPads) {
for (var footprint of pcbdata.footprints) {
for (var pad of footprint.pads) {
if (pad.layers.includes(layer) && pointWithinPad(x, y, pad)) {
return pad.net;
}
}
}
}
return null;
}

function pointWithinFootprintBbox(x, y, bbox) {
var v = [x - bbox.pos[0], y - bbox.pos[1]];
v = rotateVector(v, bbox.angle);
return bbox.relpos[0] <= v[0] && v[0] <= bbox.relpos[0] + bbox.size[0] &&
bbox.relpos[1] <= v[1] && v[1] <= bbox.relpos[1] + bbox.size[1];
}

function bboxHitScan(layer, x, y) {
var result = [];
for (var i = 0; i < pcbdata.footprints.length; i++) {
var footprint = pcbdata.footprints[i];
if (footprint.layer == layer) {
if (pointWithinFootprintBbox(x, y, footprint.bbox)) {
result.push(i);
}
}
}
return result;
}

function handlePointerDown(e, layerdict) {
if (e.button != 0 && e.button != 1) {
return;
}
e.preventDefault();
e.stopPropagation();

if (!e.hasOwnProperty("offsetX")) {
// The polyfill doesn't set this properly
e.offsetX = e.pageX - e.currentTarget.offsetLeft;
e.offsetY = e.pageY - e.currentTarget.offsetTop;
}

layerdict.pointerStates[e.pointerId] = {
distanceTravelled: 0,
lastX: e.offsetX,
lastY: e.offsetY,
downTime: Date.now(),
};
}

function handleMouseClick(e, layerdict) {
if (!e.hasOwnProperty("offsetX")) {
// The polyfill doesn't set this properly
e.offsetX = e.pageX - e.currentTarget.offsetLeft;
e.offsetY = e.pageY - e.currentTarget.offsetTop;
}

var x = e.offsetX;
var y = e.offsetY;
var t = layerdict.transform;
if (layerdict.layer == "B") {
x = (devicePixelRatio * x / t.zoom - t.panx + t.x) / -t.s;
} else {
x = (devicePixelRatio * x / t.zoom - t.panx - t.x) / t.s;
}
y = (devicePixelRatio * y / t.zoom - t.y - t.pany) / t.s;
var v = rotateVector([x, y], -settings.boardRotation);
if ("nets" in pcbdata) {
var net = netHitScan(layerdict.layer, ...v);
if (net !== highlightedNet) {
netClicked(net);
}
}
if (highlightedNet === null) {
var footprints = bboxHitScan(layerdict.layer, ...v);
if (footprints.length > 0) {
footprintsClicked(footprints);
}
}
}

function handlePointerLeave(e, layerdict) {
e.preventDefault();
e.stopPropagation();

if (!settings.redrawOnDrag) {
redrawCanvas(layerdict);
}

delete layerdict.pointerStates[e.pointerId];
}

function resetTransform(layerdict) {
layerdict.transform.panx = 0;
layerdict.transform.pany = 0;
layerdict.transform.zoom = 1;
redrawCanvas(layerdict);
}

function handlePointerUp(e, layerdict) {
if (!e.hasOwnProperty("offsetX")) {
// The polyfill doesn't set this properly
e.offsetX = e.pageX - e.currentTarget.offsetLeft;
e.offsetY = e.pageY - e.currentTarget.offsetTop;
}

e.preventDefault();
e.stopPropagation();

if (e.button == 2) {
// Reset pan and zoom on right click.
resetTransform(layerdict);
layerdict.anotherPointerTapped = false;
return;
}

// We haven't necessarily had a pointermove event since the interaction started, so make sure we update this now
var ptr = layerdict.pointerStates[e.pointerId];
ptr.distanceTravelled += Math.abs(e.offsetX - ptr.lastX) + Math.abs(e.offsetY - ptr.lastY);

if (e.button == 0 && ptr.distanceTravelled < 10 && Date.now() - ptr.downTime <= 500) {
if (Object.keys(layerdict.pointerStates).length == 1) {
if (layerdict.anotherPointerTapped) {
// This is the second pointer coming off of a two-finger tap
resetTransform(layerdict);
} else {
// This is just a regular tap
handleMouseClick(e, layerdict);
}
layerdict.anotherPointerTapped = false;
} else {
// This is the first finger coming off of what could become a two-finger tap
layerdict.anotherPointerTapped = true;
}
} else {
if (!settings.redrawOnDrag) {
redrawCanvas(layerdict);
}
layerdict.anotherPointerTapped = false;
}

delete layerdict.pointerStates[e.pointerId];
}

function handlePointerMove(e, layerdict) {
if (!layerdict.pointerStates.hasOwnProperty(e.pointerId)) {
return;
}
e.preventDefault();
e.stopPropagation();

if (!e.hasOwnProperty("offsetX")) {
// The polyfill doesn't set this properly
e.offsetX = e.pageX - e.currentTarget.offsetLeft;
e.offsetY = e.pageY - e.currentTarget.offsetTop;
}

var thisPtr = layerdict.pointerStates[e.pointerId];

var dx = e.offsetX - thisPtr.lastX;
var dy = e.offsetY - thisPtr.lastY;

// If this number is low on pointer up, we count the action as a click
thisPtr.distanceTravelled += Math.abs(dx) + Math.abs(dy);

if (Object.keys(layerdict.pointerStates).length == 1) {
// This is a simple drag
layerdict.transform.panx += devicePixelRatio * dx / layerdict.transform.zoom;
layerdict.transform.pany += devicePixelRatio * dy / layerdict.transform.zoom;
} else if (Object.keys(layerdict.pointerStates).length == 2) {
var otherPtr = Object.values(layerdict.pointerStates).filter((ptr) => ptr != thisPtr)[0];

    var oldDist = Math.sqrt(Math.pow(thisPtr.lastX - otherPtr.lastX, 2) + Math.pow(thisPtr.lastY - otherPtr.lastY, 2));
    var newDist = Math.sqrt(Math.pow(e.offsetX - otherPtr.lastX, 2) + Math.pow(e.offsetY - otherPtr.lastY, 2));

    var scaleFactor = newDist / oldDist;

    if (scaleFactor != NaN) {
      layerdict.transform.zoom *= scaleFactor;

      var zoomd = (1 - scaleFactor) / layerdict.transform.zoom;
      layerdict.transform.panx += devicePixelRatio * otherPtr.lastX * zoomd;
      layerdict.transform.pany += devicePixelRatio * otherPtr.lastY * zoomd;
    }
}

thisPtr.lastX = e.offsetX;
thisPtr.lastY = e.offsetY;

if (settings.redrawOnDrag) {
redrawCanvas(layerdict);
}
}

function handleMouseWheel(e, layerdict) {
e.preventDefault();
e.stopPropagation();
var t = layerdict.transform;
var wheeldelta = e.deltaY;
if (e.deltaMode == 1) {
// FF only, scroll by lines
wheeldelta *= 30;
} else if (e.deltaMode == 2) {
wheeldelta *= 300;
}
var m = Math.pow(1.1, -wheeldelta / 40);
// Limit amount of zoom per tick.
if (m > 2) {
m = 2;
} else if (m < 0.5) {
m = 0.5;
}
t.zoom *= m;
var zoomd = (1 - m) / t.zoom;
t.panx += devicePixelRatio * e.offsetX * zoomd;
t.pany += devicePixelRatio * e.offsetY * zoomd;
redrawCanvas(layerdict);
}

function addMouseHandlers(div, layerdict) {
div.addEventListener("pointerdown", function(e) {
handlePointerDown(e, layerdict);
});
div.addEventListener("pointermove", function(e) {
handlePointerMove(e, layerdict);
});
div.addEventListener("pointerup", function(e) {
handlePointerUp(e, layerdict);
});
var pointerleave = function(e) {
handlePointerLeave(e, layerdict);
}
div.addEventListener("pointercancel", pointerleave);
div.addEventListener("pointerleave", pointerleave);
div.addEventListener("pointerout", pointerleave);

div.onwheel = function(e) {
handleMouseWheel(e, layerdict);
}
for (var element of [div, layerdict.bg, layerdict.fab, layerdict.silk, layerdict.highlight]) {
element.addEventListener("contextmenu", function(e) {
e.preventDefault();
}, false);
}
}

function setRedrawOnDrag(value) {
settings.redrawOnDrag = value;
writeStorage("redrawOnDrag", value);
}

function setBoardRotation(value) {
settings.boardRotation = value * 5;
writeStorage("boardRotation", settings.boardRotation);
document.getElementById("rotationDegree").textContent = settings.boardRotation;
resizeAll();
}

function initRender() {
allcanvas = {
front: {
transform: {
x: 0,
y: 0,
s: 1,
panx: 0,
pany: 0,
zoom: 1,
},
pointerStates: {},
anotherPointerTapped: false,
bg: document.getElementById("F_bg"),
fab: document.getElementById("F_fab"),
silk: document.getElementById("F_slk"),
highlight: document.getElementById("F_hl"),
layer: "F",
},
back: {
transform: {
x: 0,
y: 0,
s: 1,
panx: 0,
pany: 0,
zoom: 1,
},
pointerStates: {},
anotherPointerTapped: false,
bg: document.getElementById("B_bg"),
fab: document.getElementById("B_fab"),
silk: document.getElementById("B_slk"),
highlight: document.getElementById("B_hl"),
layer: "B",
}
};
addMouseHandlers(document.getElementById("frontcanvas"), allcanvas.front);
addMouseHandlers(document.getElementById("backcanvas"), allcanvas.back);
}

///////////////////////////////////////////////

///////////////////////////////////////////////
/*
* Table reordering via Drag'n'Drop
* Inspired by: https://htmldom.dev/drag-and-drop-table-column
  */

function setBomHandlers() {

const bom = document.getElementById('bomtable');

let dragName;
let placeHolderElements;
let draggingElement;
let forcePopulation;
let xOffset;
let yOffset;
let wasDragged;

const mouseUpHandler = function(e) {
// Delete dragging element
draggingElement.remove();

    // Make BOM selectable again
    bom.style.removeProperty("userSelect");

    // Remove listeners
    document.removeEventListener('mousemove', mouseMoveHandler);
    document.removeEventListener('mouseup', mouseUpHandler);

    if (wasDragged) {
      // Redraw whole BOM
      populateBomTable();
    }
}

const mouseMoveHandler = function(e) {
// Notice the dragging
wasDragged = true;

    // Make the dragged element visible
    draggingElement.style.removeProperty("display");

    // Set elements position to mouse position
    draggingElement.style.left = `${e.screenX - xOffset}px`;
    draggingElement.style.top = `${e.screenY - yOffset}px`;

    // Forced redrawing of BOM table
    if (forcePopulation) {
      forcePopulation = false;
      // Copy array
      phe = Array.from(placeHolderElements);
      // populate BOM table again
      populateBomHeader(dragName, phe);
      populateBomBody(dragName, phe);
    }

    // Set up array of hidden columns
    var hiddenColumns = Array.from(settings.hiddenColumns);
    // In the ungrouped mode, quantity don't exist
    if (settings.bommode === "ungrouped")
      hiddenColumns.push("Quantity");
    // If no checkbox fields can be found, we consider them hidden
    if (settings.checkboxes.length == 0)
      hiddenColumns.push("checkboxes");

    // Get table headers and group them into checkboxes, extrafields and normal headers
    const bh = document.getElementById("bomhead");
    headers = Array.from(bh.querySelectorAll("th"))
    headers.shift() // numCol is not part of the columnOrder
    headerGroups = []
    lastCompoundClass = null;
    for (i = 0; i < settings.columnOrder.length; i++) {
      cElem = settings.columnOrder[i];
      if (hiddenColumns.includes(cElem)) {
        // Hidden columns appear as a dummy element
        headerGroups.push([]);
        continue;
      }
      elem = headers.filter(e => getColumnOrderName(e) === cElem)[0];
      if (elem.classList.contains("bom-checkbox")) {
        if (lastCompoundClass === "bom-checkbox") {
          cbGroup = headerGroups.pop();
          cbGroup.push(elem);
          headerGroups.push(cbGroup);
        } else {
          lastCompoundClass = "bom-checkbox";
          headerGroups.push([elem])
        }
      } else {
        headerGroups.push([elem])
      }
    }

    // Copy settings.columnOrder
    var columns = Array.from(settings.columnOrder)

    // Set up array with indices of hidden columns
    var hiddenIndices = hiddenColumns.map(e => settings.columnOrder.indexOf(e));
    var dragIndex = columns.indexOf(dragName);
    var swapIndex = dragIndex;
    var swapDone = false;

    // Check if the current dragged element is swapable with the left or right element
    if (dragIndex > 0) {
      // Get left headers boundingbox
      swapIndex = dragIndex - 1;
      while (hiddenIndices.includes(swapIndex) && swapIndex > 0)
        swapIndex--;
      if (!hiddenIndices.includes(swapIndex)) {
        box = getBoundingClientRectFromMultiple(headerGroups[swapIndex]);
        if (e.clientX < box.left + window.scrollX + (box.width / 2)) {
          swapElement = columns[dragIndex];
          columns.splice(dragIndex, 1);
          columns.splice(swapIndex, 0, swapElement);
          forcePopulation = true;
          swapDone = true;
        }
      }
    }
    if ((!swapDone) && dragIndex < headerGroups.length - 1) {
      // Get right headers boundingbox
      swapIndex = dragIndex + 1;
      while (hiddenIndices.includes(swapIndex))
        swapIndex++;
      if (swapIndex < headerGroups.length) {
        box = getBoundingClientRectFromMultiple(headerGroups[swapIndex]);
        if (e.clientX > box.left + window.scrollX + (box.width / 2)) {
          swapElement = columns[dragIndex];
          columns.splice(dragIndex, 1);
          columns.splice(swapIndex, 0, swapElement);
          forcePopulation = true;
          swapDone = true;
        }
      }
    }

    // Write back change to storage
    if (swapDone) {
      settings.columnOrder = columns
      writeStorage("columnOrder", JSON.stringify(columns));
    }

}

const mouseDownHandler = function(e) {
var target = e.target;
if (target.tagName.toLowerCase() != "td")
target = target.parentElement;

    // Used to check if a dragging has ever happened
    wasDragged = false;

    // Create new element which will be displayed as the dragged column
    draggingElement = document.createElement("div")
    draggingElement.classList.add("dragging");
    draggingElement.style.display = "none";
    draggingElement.style.position = "absolute";
    draggingElement.style.overflow = "hidden";

    // Get bomhead and bombody elements
    const bh = document.getElementById("bomhead");
    const bb = document.getElementById("bombody");

    // Get all compound headers for the current column
    var compoundHeaders;
    if (target.classList.contains("bom-checkbox")) {
      compoundHeaders = Array.from(bh.querySelectorAll("th.bom-checkbox"));
    } else {
      compoundHeaders = [target];
    }

    // Create new table which will display the column
    var newTable = document.createElement("table");
    newTable.classList.add("bom");
    newTable.style.background = "white";
    draggingElement.append(newTable);

    // Create new header element
    var newHeader = document.createElement("thead");
    newTable.append(newHeader);

    // Set up array for storing all placeholder elements
    placeHolderElements = [];

    // Add all compound headers to the new thead element and placeholders
    compoundHeaders.forEach(function(h) {
      clone = cloneElementWithDimensions(h);
      newHeader.append(clone);
      placeHolderElements.push(clone);
    });

    // Create new body element
    var newBody = document.createElement("tbody");
    newTable.append(newBody);

    // Get indices for compound headers
    var idxs = compoundHeaders.map(e => getBomTableHeaderIndex(e));

    // For each row in the BOM body...
    var rows = bb.querySelectorAll("tr");
    rows.forEach(function(row) {
      // ..get the cells for the compound column
      const tds = row.querySelectorAll("td");
      var copytds = idxs.map(i => tds[i]);
      // Add them to the new element and the placeholders
      var newRow = document.createElement("tr");
      copytds.forEach(function(td) {
        clone = cloneElementWithDimensions(td);
        newRow.append(clone);
        placeHolderElements.push(clone);
      });
      newBody.append(newRow);
    });

    // Compute width for compound header
    var width = compoundHeaders.reduce((acc, x) => acc + x.clientWidth, 0);
    draggingElement.style.width = `${width}px`;

    // Insert the new dragging element and disable selection on BOM
    bom.insertBefore(draggingElement, null);
    bom.style.userSelect = "none";

    // Determine the mouse position offset
    xOffset = e.screenX - compoundHeaders.reduce((acc, x) => Math.min(acc, x.offsetLeft), compoundHeaders[0].offsetLeft);
    yOffset = e.screenY - compoundHeaders[0].offsetTop;

    // Get name for the column in settings.columnOrder
    dragName = getColumnOrderName(target);

    // Change text and class for placeholder elements
    placeHolderElements = placeHolderElements.map(function(e) {
      newElem = cloneElementWithDimensions(e);
      newElem.textContent = "";
      newElem.classList.add("placeholder");
      return newElem;
    });

    // On next mouse move, the whole BOM needs to be redrawn to show the placeholders
    forcePopulation = true;

    // Add listeners for move and up on mouse
    document.addEventListener('mousemove', mouseMoveHandler);
    document.addEventListener('mouseup', mouseUpHandler);
}

// In netlist mode, there is nothing to reorder
if (settings.bommode === "netlist")
return;

// Add mouseDownHandler to every column except the numCol
bom.querySelectorAll("th")
.forEach(function(head) {
if (!head.classList.contains("numCol")) {
head.onmousedown = mouseDownHandler;
}
});

}

function getBoundingClientRectFromMultiple(elements) {
var elems = Array.from(elements);

if (elems.length == 0)
return null;

var box = elems.shift()
.getBoundingClientRect();

elems.forEach(function(elem) {
var elembox = elem.getBoundingClientRect();
box.left = Math.min(elembox.left, box.left);
box.top = Math.min(elembox.top, box.top);
box.width += elembox.width;
box.height = Math.max(elembox.height, box.height);
});

return box;
}

function cloneElementWithDimensions(elem) {
var newElem = elem.cloneNode(true);
newElem.style.height = window.getComputedStyle(elem).height;
newElem.style.width = window.getComputedStyle(elem).width;
return newElem;
}

function getBomTableHeaderIndex(elem) {
const bh = document.getElementById('bomhead');
const ths = Array.from(bh.querySelectorAll("th"));
return ths.indexOf(elem);
}

function getColumnOrderName(elem) {
var cname = elem.getAttribute("col_name");
if (cname === "bom-checkbox")
return "checkboxes";
else
return cname;
}

function resizableGrid(tablehead) {
var cols = tablehead.firstElementChild.children;
var rowWidth = tablehead.offsetWidth;

for (var i = 1; i < cols.length; i++) {
if (cols[i].classList.contains("bom-checkbox"))
continue;
cols[i].style.width = ((cols[i].clientWidth - paddingDiff(cols[i])) * 100 / rowWidth) + '%';
}

for (var i = 1; i < cols.length - 1; i++) {
var div = document.createElement('div');
div.className = "column-width-handle";
cols[i].appendChild(div);
setListeners(div);
}

function setListeners(div) {
var startX, curCol, nxtCol, curColWidth, nxtColWidth, rowWidth;

    div.addEventListener('mousedown', function(e) {
      e.preventDefault();
      e.stopPropagation();

      curCol = e.target.parentElement;
      nxtCol = curCol.nextElementSibling;
      startX = e.pageX;

      var padding = paddingDiff(curCol);

      rowWidth = curCol.parentElement.offsetWidth;
      curColWidth = curCol.clientWidth - padding;
      nxtColWidth = nxtCol.clientWidth - padding;
    });

    document.addEventListener('mousemove', function(e) {
      if (startX) {
        var diffX = e.pageX - startX;
        diffX = -Math.min(-diffX, curColWidth - 20);
        diffX = Math.min(diffX, nxtColWidth - 20);

        curCol.style.width = ((curColWidth + diffX) * 100 / rowWidth) + '%';
        nxtCol.style.width = ((nxtColWidth - diffX) * 100 / rowWidth) + '%';
        console.log(`${curColWidth + nxtColWidth} ${(curColWidth + diffX) * 100 / rowWidth + (nxtColWidth - diffX) * 100 / rowWidth}`);
      }
    });

    document.addEventListener('mouseup', function(e) {
      curCol = undefined;
      nxtCol = undefined;
      startX = undefined;
      nxtColWidth = undefined;
      curColWidth = undefined
    });
}

function paddingDiff(col) {

    if (getStyleVal(col, 'box-sizing') == 'border-box') {
      return 0;
    }

    var padLeft = getStyleVal(col, 'padding-left');
    var padRight = getStyleVal(col, 'padding-right');
    return (parseInt(padLeft) + parseInt(padRight));

}

function getStyleVal(elm, css) {
return (window.getComputedStyle(elm, null).getPropertyValue(css))
}
}

///////////////////////////////////////////////

///////////////////////////////////////////////
/* DOM manipulation and misc code */

var bomsplit;
var canvassplit;
var initDone = false;
var bomSortFunction = null;
var currentSortColumn = null;
var currentSortOrder = null;
var currentHighlightedRowId;
var highlightHandlers = [];
var footprintIndexToHandler = {};
var netsToHandler = {};
var markedFootprints = new Set();
var highlightedFootprints = [];
var highlightedNet = null;
var lastClicked;

function dbg(html) {
dbgdiv.innerHTML = html;
}

function redrawIfInitDone() {
if (initDone) {
redrawCanvas(allcanvas.front);
redrawCanvas(allcanvas.back);
}
}

function padsVisible(value) {
writeStorage("padsVisible", value);
settings.renderPads = value;
redrawIfInitDone();
}

function referencesVisible(value) {
writeStorage("referencesVisible", value);
settings.renderReferences = value;
redrawIfInitDone();
}

function valuesVisible(value) {
writeStorage("valuesVisible", value);
settings.renderValues = value;
redrawIfInitDone();
}

function tracksVisible(value) {
writeStorage("tracksVisible", value);
settings.renderTracks = value;
redrawIfInitDone();
}

function zonesVisible(value) {
writeStorage("zonesVisible", value);
settings.renderZones = value;
redrawIfInitDone();
}

function dnpOutline(value) {
writeStorage("dnpOutline", value);
settings.renderDnpOutline = value;
redrawIfInitDone();
}

function setDarkMode(value) {
if (value) {
topmostdiv.classList.add("dark");
} else {
topmostdiv.classList.remove("dark");
}
writeStorage("darkmode", value);
settings.darkMode = value;
redrawIfInitDone();
}

function setShowBOMColumn(field, value) {
if (field === "references") {
var rl = document.getElementById("reflookup");
rl.disabled = !value;
if (!value) {
rl.value = "";
updateRefLookup("");
}
}

var n = settings.hiddenColumns.indexOf(field);
if (value) {
if (n != -1) {
settings.hiddenColumns.splice(n, 1);
}
} else {
if (n == -1) {
settings.hiddenColumns.push(field);
}
}

writeStorage("hiddenColumns", JSON.stringify(settings.hiddenColumns));

if (initDone) {
populateBomTable();
}

redrawIfInitDone();
}


function setFullscreen(value) {
if (value) {
document.documentElement.requestFullscreen();
} else {
document.exitFullscreen();
}
}

function fabricationVisible(value) {
writeStorage("fabricationVisible", value);
settings.renderFabrication = value;
redrawIfInitDone();
}

function silkscreenVisible(value) {
writeStorage("silkscreenVisible", value);
settings.renderSilkscreen = value;
redrawIfInitDone();
}

function setHighlightPin1(value) {
writeStorage("highlightpin1", value);
settings.highlightpin1 = value;
redrawIfInitDone();
}

function getStoredCheckboxRefs(checkbox) {
function convert(ref) {
var intref = parseInt(ref);
if (isNaN(intref)) {
for (var i = 0; i < pcbdata.footprints.length; i++) {
if (pcbdata.footprints[i].ref == ref) {
return i;
}
}
return -1;
} else {
return intref;
}
}
if (!(checkbox in settings.checkboxStoredRefs)) {
var val = readStorage("checkbox_" + checkbox);
settings.checkboxStoredRefs[checkbox] = val ? val : "";
}
if (!settings.checkboxStoredRefs[checkbox]) {
return new Set();
} else {
return new Set(settings.checkboxStoredRefs[checkbox].split(",").map(r => convert(r)).filter(a => a >= 0));
}
}

function getCheckboxState(checkbox, references) {
var storedRefsSet = getStoredCheckboxRefs(checkbox);
var currentRefsSet = new Set(references.map(r => r[1]));
// Get difference of current - stored
var difference = new Set(currentRefsSet);
for (ref of storedRefsSet) {
difference.delete(ref);
}
if (difference.size == 0) {
// All the current refs are stored
return "checked";
} else if (difference.size == currentRefsSet.size) {
// None of the current refs are stored
return "unchecked";
} else {
// Some of the refs are stored
return "indeterminate";
}
}

function setBomCheckboxState(checkbox, element, references) {
var state = getCheckboxState(checkbox, references);
element.checked = (state == "checked");
element.indeterminate = (state == "indeterminate");
}

function createCheckboxChangeHandler(checkbox, references, row) {
return function () {
refsSet = getStoredCheckboxRefs(checkbox);
var markWhenChecked = settings.markWhenChecked == checkbox;
eventArgs = {
checkbox: checkbox,
refs: references,
}
if (this.checked) {
// checkbox ticked
for (var ref of references) {
refsSet.add(ref[1]);
}
if (markWhenChecked) {
row.classList.add("checked");
for (var ref of references) {
markedFootprints.add(ref[1]);
}
drawHighlights();
}
eventArgs.state = 'checked';
} else {
// checkbox unticked
for (var ref of references) {
refsSet.delete(ref[1]);
}
if (markWhenChecked) {
row.classList.remove("checked");
for (var ref of references) {
markedFootprints.delete(ref[1]);
}
drawHighlights();
}
eventArgs.state = 'unchecked';
}
settings.checkboxStoredRefs[checkbox] = [...refsSet].join(",");
writeStorage("checkbox_" + checkbox, settings.checkboxStoredRefs[checkbox]);
updateCheckboxStats(checkbox);
EventHandler.emitEvent(IBOM_EVENT_TYPES.CHECKBOX_CHANGE_EVENT, eventArgs);
}
}

function clearHighlightedFootprints() {
if (currentHighlightedRowId) {
document.getElementById(currentHighlightedRowId).classList.remove("highlighted");
currentHighlightedRowId = null;
highlightedFootprints = [];
highlightedNet = null;
}
}

function createRowHighlightHandler(rowid, refs, net) {
return function () {
if (currentHighlightedRowId) {
if (currentHighlightedRowId == rowid) {
return;
}
document.getElementById(currentHighlightedRowId).classList.remove("highlighted");
}
document.getElementById(rowid).classList.add("highlighted");
currentHighlightedRowId = rowid;
highlightedFootprints = refs ? refs.map(r => r[1]) : [];
highlightedNet = net;
drawHighlights();
EventHandler.emitEvent(
IBOM_EVENT_TYPES.HIGHLIGHT_EVENT, {
rowid: rowid,
refs: refs,
net: net
});
}
}

function entryMatches(entry) {
if (settings.bommode == "netlist") {
// entry is just a net name
return entry.toLowerCase().indexOf(filter) >= 0;
}
// check refs
if (!settings.hiddenColumns.includes("references")) {
for (var ref of entry) {
if (ref[0].toLowerCase().indexOf(filter) >= 0) {
return true;
}
}
}
// check fields
for (var i in config.fields) {
var f = config.fields[i];
if (!settings.hiddenColumns.includes(f)) {
for (var ref of entry) {
if (pcbdata.bom.fields[ref[1]][i].toLowerCase().indexOf(filter) >= 0) {
return true;
}
}
}
}
return false;
}

function findRefInEntry(entry) {
return entry.filter(r => r[0].toLowerCase() == reflookup);
}

function highlightFilter(s) {
if (!filter) {
return s;
}
var parts = s.toLowerCase().split(filter);
if (parts.length == 1) {
return s;
}
var r = "";
var pos = 0;
for (var i in parts) {
if (i > 0) {
r += '<mark class="highlight">' +
s.substring(pos, pos + filter.length) +
'</mark>';
pos += filter.length;
}
r += s.substring(pos, pos + parts[i].length);
pos += parts[i].length;
}
return r;
}

function checkboxSetUnsetAllHandler(checkboxname) {
return function () {
var checkboxnum = 0;
while (checkboxnum < settings.checkboxes.length &&
settings.checkboxes[checkboxnum].toLowerCase() != checkboxname.toLowerCase()) {
checkboxnum++;
}
if (checkboxnum >= settings.checkboxes.length) {
return;
}
var allset = true;
var checkbox;
var row;
for (row of bombody.childNodes) {
checkbox = row.childNodes[checkboxnum + 1].childNodes[0];
if (!checkbox.checked || checkbox.indeterminate) {
allset = false;
break;
}
}
for (row of bombody.childNodes) {
checkbox = row.childNodes[checkboxnum + 1].childNodes[0];
checkbox.checked = !allset;
checkbox.indeterminate = false;
checkbox.onchange();
}
}
}

function createColumnHeader(name, cls, comparator, is_checkbox = false) {
var th = document.createElement("TH");
th.innerHTML = name;
th.classList.add(cls);
if (is_checkbox)
th.setAttribute("col_name", "bom-checkbox");
else
th.setAttribute("col_name", name);
var span = document.createElement("SPAN");
span.classList.add("sortmark");
span.classList.add("none");
th.appendChild(span);
var spacer = document.createElement("div");
spacer.className = "column-spacer";
th.appendChild(spacer);
spacer.onclick = function () {
if (currentSortColumn && th !== currentSortColumn) {
// Currently sorted by another column
currentSortColumn.childNodes[1].classList.remove(currentSortOrder);
currentSortColumn.childNodes[1].classList.add("none");
currentSortColumn = null;
currentSortOrder = null;
}
if (currentSortColumn && th === currentSortColumn) {
// Already sorted by this column
if (currentSortOrder == "asc") {
// Sort by this column, descending order
bomSortFunction = function (a, b) {
return -comparator(a, b);
}
currentSortColumn.childNodes[1].classList.remove("asc");
currentSortColumn.childNodes[1].classList.add("desc");
currentSortOrder = "desc";
} else {
// Unsort
bomSortFunction = null;
currentSortColumn.childNodes[1].classList.remove("desc");
currentSortColumn.childNodes[1].classList.add("none");
currentSortColumn = null;
currentSortOrder = null;
}
} else {
// Sort by this column, ascending order
bomSortFunction = comparator;
currentSortColumn = th;
currentSortColumn.childNodes[1].classList.remove("none");
currentSortColumn.childNodes[1].classList.add("asc");
currentSortOrder = "asc";
}
populateBomBody();
}
if (is_checkbox) {
spacer.onclick = fancyDblClickHandler(
spacer, spacer.onclick, checkboxSetUnsetAllHandler(name));
}
return th;
}

function populateBomHeader(placeHolderColumn = null, placeHolderElements = null) {
while (bomhead.firstChild) {
bomhead.removeChild(bomhead.firstChild);
}
var tr = document.createElement("TR");
var th = document.createElement("TH");
th.classList.add("numCol");

var vismenu = document.createElement("div");
vismenu.id = "vismenu";
vismenu.classList.add("menu");

var visbutton = document.createElement("div");
visbutton.classList.add("visbtn");
visbutton.classList.add("hideonprint");

var viscontent = document.createElement("div");
viscontent.classList.add("menu-content");
viscontent.id = "vismenu-content";

settings.columnOrder.forEach(column => {
if (typeof column !== "string")
return;

    // Skip empty columns
    if (column === "checkboxes" && settings.checkboxes.length == 0)
      return;
    else if (column === "Quantity" && settings.bommode == "ungrouped")
      return;

    var label = document.createElement("label");
    label.classList.add("menu-label");

    var input = document.createElement("input");
    input.classList.add("visibility_checkbox");
    input.type = "checkbox";
    input.onchange = function (e) {
      setShowBOMColumn(column, e.target.checked)
    };
    input.checked = !(settings.hiddenColumns.includes(column));

    label.appendChild(input);
    if (column.length > 0)
      label.append(column[0].toUpperCase() + column.slice(1));

    viscontent.appendChild(label);
});

viscontent.childNodes[0].classList.add("menu-label-top");

vismenu.appendChild(visbutton);
if (settings.bommode != "netlist") {
vismenu.appendChild(viscontent);
th.appendChild(vismenu);
}
tr.appendChild(th);

var checkboxCompareClosure = function (checkbox) {
return (a, b) => {
var stateA = getCheckboxState(checkbox, a);
var stateB = getCheckboxState(checkbox, b);
if (stateA > stateB) return -1;
if (stateA < stateB) return 1;
return 0;
}
}
var stringFieldCompareClosure = function (fieldIndex) {
return (a, b) => {
var fa = pcbdata.bom.fields[a[0][1]][fieldIndex];
var fb = pcbdata.bom.fields[b[0][1]][fieldIndex];
if (fa != fb) return fa > fb ? 1 : -1;
else return 0;
}
}
var referenceRegex = /(?<prefix>[^0-9]+)(?<number>[0-9]+)/;
var compareRefs = (a, b) => {
var ra = referenceRegex.exec(a);
var rb = referenceRegex.exec(b);
if (ra === null || rb === null) {
if (a != b) return a > b ? 1 : -1;
return 0;
} else {
if (ra.groups.prefix != rb.groups.prefix) {
return ra.groups.prefix > rb.groups.prefix ? 1 : -1;
}
if (ra.groups.number != rb.groups.number) {
return parseInt(ra.groups.number) > parseInt(rb.groups.number) ? 1 : -1;
}
return 0;
}
}
if (settings.bommode == "netlist") {
th = createColumnHeader("Net name", "bom-netname", (a, b) => {
if (a > b) return -1;
if (a < b) return 1;
return 0;
});
tr.appendChild(th);
} else {
// Filter hidden columns
var columns = settings.columnOrder.filter(e => !settings.hiddenColumns.includes(e));
var valueIndex = config.fields.indexOf("Value");
var footprintIndex = config.fields.indexOf("Footprint");
columns.forEach((column) => {
if (column === placeHolderColumn) {
var n = 1;
if (column === "checkboxes")
n = settings.checkboxes.length;
for (i = 0; i < n; i++) {
td = placeHolderElements.shift();
tr.appendChild(td);
}
return;
} else if (column === "checkboxes") {
for (var checkbox of settings.checkboxes) {
th = createColumnHeader(
checkbox, "bom-checkbox", checkboxCompareClosure(checkbox), true);
tr.appendChild(th);
}
} else if (column === "References") {
tr.appendChild(createColumnHeader("References", "references", (a, b) => {
var i = 0;
while (i < a.length && i < b.length) {
if (a[i] != b[i]) return compareRefs(a[i][0], b[i][0]);
i++;
}
return a.length - b.length;
}));
} else if (column === "Value") {
tr.appendChild(createColumnHeader("Value", "value", (a, b) => {
var ra = a[0][1], rb = b[0][1];
return valueCompare(
pcbdata.bom.parsedValues[ra], pcbdata.bom.parsedValues[rb],
pcbdata.bom.fields[ra][valueIndex], pcbdata.bom.fields[rb][valueIndex]);
}));
return;
} else if (column === "Footprint") {
tr.appendChild(createColumnHeader(
"Footprint", "footprint", stringFieldCompareClosure(footprintIndex)));
} else if (column === "Quantity" && settings.bommode == "grouped") {
tr.appendChild(createColumnHeader("Quantity", "quantity", (a, b) => {
return a.length - b.length;
}));
} else {
// Other fields
var i = config.fields.indexOf(column);
if (i < 0)
return;
tr.appendChild(createColumnHeader(
column, `field${i + 1}`, stringFieldCompareClosure(i)));
}
});
}
bomhead.appendChild(tr);
}

function populateBomBody(placeholderColumn = null, placeHolderElements = null) {
while (bom.firstChild) {
bom.removeChild(bom.firstChild);
}
highlightHandlers = [];
footprintIndexToHandler = {};
netsToHandler = {};
currentHighlightedRowId = null;
var first = true;
if (settings.bommode == "netlist") {
bomtable = pcbdata.nets.slice();
} else {
switch (settings.canvaslayout) {
case 'F':
bomtable = pcbdata.bom.F.slice();
break;
case 'FB':
bomtable = pcbdata.bom.both.slice();
break;
case 'B':
bomtable = pcbdata.bom.B.slice();
break;
}
if (settings.bommode == "ungrouped") {
// expand bom table
expandedTable = []
for (var bomentry of bomtable) {
for (var ref of bomentry) {
expandedTable.push([ref]);
}
}
bomtable = expandedTable;
}
}
if (bomSortFunction) {
bomtable = bomtable.sort(bomSortFunction);
}
for (var i in bomtable) {
var bomentry = bomtable[i];
if (filter && !entryMatches(bomentry)) {
continue;
}
var references = null;
var netname = null;
var tr = document.createElement("TR");
var td = document.createElement("TD");
var rownum = +i + 1;
tr.id = "bomrow" + rownum;
td.textContent = rownum;
tr.appendChild(td);
if (settings.bommode == "netlist") {
netname = bomentry;
td = document.createElement("TD");
td.innerHTML = highlightFilter(netname ? netname : "&lt;no net&gt;");
tr.appendChild(td);
} else {
if (reflookup) {
references = findRefInEntry(bomentry);
if (references.length == 0) {
continue;
}
} else {
references = bomentry;
}
// Filter hidden columns
var columns = settings.columnOrder.filter(e => !settings.hiddenColumns.includes(e));
columns.forEach((column) => {
if (column === placeholderColumn) {
var n = 1;
if (column === "checkboxes")
n = settings.checkboxes.length;
for (i = 0; i < n; i++) {
td = placeHolderElements.shift();
tr.appendChild(td);
}
return;
} else if (column === "checkboxes") {
for (var checkbox of settings.checkboxes) {
if (checkbox) {
td = document.createElement("TD");
var input = document.createElement("input");
input.type = "checkbox";
input.onchange = createCheckboxChangeHandler(checkbox, references, tr);
setBomCheckboxState(checkbox, input, references);
if (input.checked && settings.markWhenChecked == checkbox) {
tr.classList.add("checked");
}
td.appendChild(input);
tr.appendChild(td);
}
}
} else if (column === "References") {
td = document.createElement("TD");
td.innerHTML = highlightFilter(references.map(r => r[0]).join(", "));
tr.appendChild(td);
} else if (column === "Quantity" && settings.bommode == "grouped") {
// Quantity
td = document.createElement("TD");
td.textContent = references.length;
tr.appendChild(td);
} else {
// All the other fields
var field_index = config.fields.indexOf(column)
if (field_index < 0)
return;
var valueSet = new Set();
references.map(r => r[1]).forEach((id) => valueSet.add(pcbdata.bom.fields[id][field_index]));
td = document.createElement("TD");
td.innerHTML = highlightFilter(Array.from(valueSet).join(", "));
tr.appendChild(td);
}
});
}
bom.appendChild(tr);
var handler = createRowHighlightHandler(tr.id, references, netname);
tr.onmousemove = handler;
highlightHandlers.push({
id: tr.id,
handler: handler,
});
if (references !== null) {
for (var refIndex of references.map(r => r[1])) {
footprintIndexToHandler[refIndex] = handler;
}
}
if (netname !== null) {
netsToHandler[netname] = handler;
}
if ((filter || reflookup) && first) {
handler();
first = false;
}
}
EventHandler.emitEvent(
IBOM_EVENT_TYPES.BOM_BODY_CHANGE_EVENT, {
filter: filter,
reflookup: reflookup,
checkboxes: settings.checkboxes,
bommode: settings.bommode,
});
}

function highlightPreviousRow() {
if (!currentHighlightedRowId) {
highlightHandlers[highlightHandlers.length - 1].handler();
} else {
if (highlightHandlers.length > 1 &&
highlightHandlers[0].id == currentHighlightedRowId) {
highlightHandlers[highlightHandlers.length - 1].handler();
} else {
for (var i = 0; i < highlightHandlers.length - 1; i++) {
if (highlightHandlers[i + 1].id == currentHighlightedRowId) {
highlightHandlers[i].handler();
break;
}
}
}
}
smoothScrollToRow(currentHighlightedRowId);
}

function highlightNextRow() {
if (!currentHighlightedRowId) {
highlightHandlers[0].handler();
} else {
if (highlightHandlers.length > 1 &&
highlightHandlers[highlightHandlers.length - 1].id == currentHighlightedRowId) {
highlightHandlers[0].handler();
} else {
for (var i = 1; i < highlightHandlers.length; i++) {
if (highlightHandlers[i - 1].id == currentHighlightedRowId) {
highlightHandlers[i].handler();
break;
}
}
}
}
smoothScrollToRow(currentHighlightedRowId);
}

function populateBomTable() {
populateBomHeader();
populateBomBody();
setBomHandlers();
resizableGrid(bomhead);
}

function footprintsClicked(footprintIndexes) {
var lastClickedIndex = footprintIndexes.indexOf(lastClicked);
for (var i = 1; i <= footprintIndexes.length; i++) {
var refIndex = footprintIndexes[(lastClickedIndex + i) % footprintIndexes.length];
if (refIndex in footprintIndexToHandler) {
lastClicked = refIndex;
footprintIndexToHandler[refIndex]();
smoothScrollToRow(currentHighlightedRowId);
break;
}
}
}

function netClicked(net) {
if (net in netsToHandler) {
netsToHandler[net]();
smoothScrollToRow(currentHighlightedRowId);
} else {
clearHighlightedFootprints();
highlightedNet = net;
drawHighlights();
}
}

function updateFilter(input) {
filter = input.toLowerCase();
populateBomTable();
}

function updateRefLookup(input) {
reflookup = input.toLowerCase();
populateBomTable();
}

function changeCanvasLayout(layout) {
document.getElementById("fl-btn").classList.remove("depressed");
document.getElementById("fb-btn").classList.remove("depressed");
document.getElementById("bl-btn").classList.remove("depressed");
switch (layout) {
case 'F':
document.getElementById("fl-btn").classList.add("depressed");
if (settings.bomlayout != "bom-only") {
canvassplit.collapse(1);
}
break;
case 'B':
document.getElementById("bl-btn").classList.add("depressed");
if (settings.bomlayout != "bom-only") {
canvassplit.collapse(0);
}
break;
default:
document.getElementById("fb-btn").classList.add("depressed");
if (settings.bomlayout != "bom-only") {
canvassplit.setSizes([50, 50]);
}
}
settings.canvaslayout = layout;
writeStorage("canvaslayout", layout);
resizeAll();
changeBomMode(settings.bommode);
}

function populateMetadata() {
document.getElementById("title").innerHTML = pcbdata.metadata.title;
document.getElementById("revision").innerHTML = "Rev: " + pcbdata.metadata.revision;
document.getElementById("company").innerHTML = pcbdata.metadata.company;
document.getElementById("filedate").innerHTML = pcbdata.metadata.date;
if (pcbdata.metadata.title != "") {
document.title = pcbdata.metadata.title + " BOM";
}
// Calculate board stats
var fp_f = 0,
fp_b = 0,
pads_f = 0,
pads_b = 0,
pads_th = 0;
for (var i = 0; i < pcbdata.footprints.length; i++) {
if (pcbdata.bom.skipped.includes(i)) continue;
var mod = pcbdata.footprints[i];
if (mod.layer == "F") {
fp_f++;
} else {
fp_b++;
}
for (var pad of mod.pads) {
if (pad.type == "th") {
pads_th++;
} else {
if (pad.layers.includes("F")) {
pads_f++;
}
if (pad.layers.includes("B")) {
pads_b++;
}
}
}
}
document.getElementById("stats-components-front").innerHTML = fp_f;
document.getElementById("stats-components-back").innerHTML = fp_b;
document.getElementById("stats-components-total").innerHTML = fp_f + fp_b;
document.getElementById("stats-groups-front").innerHTML = pcbdata.bom.F.length;
document.getElementById("stats-groups-back").innerHTML = pcbdata.bom.B.length;
document.getElementById("stats-groups-total").innerHTML = pcbdata.bom.both.length;
document.getElementById("stats-smd-pads-front").innerHTML = pads_f;
document.getElementById("stats-smd-pads-back").innerHTML = pads_b;
document.getElementById("stats-smd-pads-total").innerHTML = pads_f + pads_b;
document.getElementById("stats-th-pads").innerHTML = pads_th;
// Update version string
document.getElementById("github-link").innerHTML = "InteractiveHtmlBom&nbsp;" +
/^v\d+\.\d+/.exec(pcbdata.ibom_version)[0];
}

function changeBomLayout(layout) {
document.getElementById("bom-btn").classList.remove("depressed");
document.getElementById("lr-btn").classList.remove("depressed");
document.getElementById("tb-btn").classList.remove("depressed");
switch (layout) {
case 'bom-only':
document.getElementById("bom-btn").classList.add("depressed");
if (bomsplit) {
bomsplit.destroy();
bomsplit = null;
canvassplit.destroy();
canvassplit = null;
}
document.getElementById("frontcanvas").style.display = "none";
document.getElementById("backcanvas").style.display = "none";
document.getElementById("bot").style.height = "";
break;
case 'top-bottom':
document.getElementById("tb-btn").classList.add("depressed");
document.getElementById("frontcanvas").style.display = "";
document.getElementById("backcanvas").style.display = "";
document.getElementById("bot").style.height = "calc(100% - 80px)";
document.getElementById("bomdiv").classList.remove("split-horizontal");
document.getElementById("canvasdiv").classList.remove("split-horizontal");
document.getElementById("frontcanvas").classList.add("split-horizontal");
document.getElementById("backcanvas").classList.add("split-horizontal");
if (bomsplit) {
bomsplit.destroy();
bomsplit = null;
canvassplit.destroy();
canvassplit = null;
}
bomsplit = Split(['#bomdiv', '#canvasdiv'], {
sizes: [50, 50],
onDragEnd: resizeAll,
direction: "vertical",
gutterSize: 5
});
canvassplit = Split(['#frontcanvas', '#backcanvas'], {
sizes: [50, 50],
gutterSize: 5,
onDragEnd: resizeAll
});
break;
case 'left-right':
document.getElementById("lr-btn").classList.add("depressed");
document.getElementById("frontcanvas").style.display = "";
document.getElementById("backcanvas").style.display = "";
document.getElementById("bot").style.height = "calc(100% - 80px)";
document.getElementById("bomdiv").classList.add("split-horizontal");
document.getElementById("canvasdiv").classList.add("split-horizontal");
document.getElementById("frontcanvas").classList.remove("split-horizontal");
document.getElementById("backcanvas").classList.remove("split-horizontal");
if (bomsplit) {
bomsplit.destroy();
bomsplit = null;
canvassplit.destroy();
canvassplit = null;
}
bomsplit = Split(['#bomdiv', '#canvasdiv'], {
sizes: [50, 50],
onDragEnd: resizeAll,
gutterSize: 5
});
canvassplit = Split(['#frontcanvas', '#backcanvas'], {
sizes: [50, 50],
gutterSize: 5,
direction: "vertical",
onDragEnd: resizeAll
});
}
settings.bomlayout = layout;
writeStorage("bomlayout", layout);
changeCanvasLayout(settings.canvaslayout);
}

function changeBomMode(mode) {
document.getElementById("bom-grouped-btn").classList.remove("depressed");
document.getElementById("bom-ungrouped-btn").classList.remove("depressed");
document.getElementById("bom-netlist-btn").classList.remove("depressed");
var chkbxs = document.getElementsByClassName("visibility_checkbox");

switch (mode) {
case 'grouped':
document.getElementById("bom-grouped-btn").classList.add("depressed");
for (var i = 0; i < chkbxs.length; i++) {
chkbxs[i].disabled = false;
}
break;
case 'ungrouped':
document.getElementById("bom-ungrouped-btn").classList.add("depressed");
for (var i = 0; i < chkbxs.length; i++) {
chkbxs[i].disabled = false;
}
break;
case 'netlist':
document.getElementById("bom-netlist-btn").classList.add("depressed");
for (var i = 0; i < chkbxs.length; i++) {
chkbxs[i].disabled = true;
}
}

writeStorage("bommode", mode);
if (mode != settings.bommode) {
settings.bommode = mode;
bomSortFunction = null;
currentSortColumn = null;
currentSortOrder = null;
clearHighlightedFootprints();
}
populateBomTable();
}

function focusFilterField() {
focusInputField(document.getElementById("filter"));
}

function focusRefLookupField() {
focusInputField(document.getElementById("reflookup"));
}

function toggleBomCheckbox(bomrowid, checkboxnum) {
if (!bomrowid || checkboxnum > settings.checkboxes.length) {
return;
}
var bomrow = document.getElementById(bomrowid);
var checkbox = bomrow.childNodes[checkboxnum].childNodes[0];
checkbox.checked = !checkbox.checked;
checkbox.indeterminate = false;
checkbox.onchange();
}

function checkBomCheckbox(bomrowid, checkboxname) {
var checkboxnum = 0;
while (checkboxnum < settings.checkboxes.length &&
settings.checkboxes[checkboxnum].toLowerCase() != checkboxname.toLowerCase()) {
checkboxnum++;
}
if (!bomrowid || checkboxnum >= settings.checkboxes.length) {
return;
}
var bomrow = document.getElementById(bomrowid);
var checkbox = bomrow.childNodes[checkboxnum + 1].childNodes[0];
checkbox.checked = true;
checkbox.indeterminate = false;
checkbox.onchange();
}

function setBomCheckboxes(value) {
writeStorage("bomCheckboxes", value);
settings.checkboxes = value.split(",").map((e) => e.trim()).filter((e) => e);
prepCheckboxes();
populateMarkWhenCheckedOptions();
setMarkWhenChecked(settings.markWhenChecked);
}

function setMarkWhenChecked(value) {
writeStorage("markWhenChecked", value);
settings.markWhenChecked = value;
markedFootprints.clear();
for (var ref of (value ? getStoredCheckboxRefs(value) : [])) {
markedFootprints.add(ref);
}
populateBomTable();
drawHighlights();
}

function prepCheckboxes() {
var table = document.getElementById("checkbox-stats");
while (table.childElementCount > 1) {
table.removeChild(table.lastChild);
}
if (settings.checkboxes.length) {
table.style.display = "";
} else {
table.style.display = "none";
}
for (var checkbox of settings.checkboxes) {
var tr = document.createElement("TR");
var td = document.createElement("TD");
td.innerHTML = checkbox;
tr.appendChild(td);
td = document.createElement("TD");
td.id = "checkbox-stats-" + checkbox;
var progressbar = document.createElement("div");
progressbar.classList.add("bar");
td.appendChild(progressbar);
var text = document.createElement("div");
text.classList.add("text");
td.appendChild(text);
tr.appendChild(td);
table.appendChild(tr);
updateCheckboxStats(checkbox);
}
}

function populateMarkWhenCheckedOptions() {
var container = document.getElementById("markWhenCheckedContainer");

if (settings.checkboxes.length == 0) {
container.parentElement.style.display = "none";
return;
}

container.innerHTML = '';
container.parentElement.style.display = "inline-block";

function createOption(name, displayName) {
var id = "markWhenChecked-" + name;

    var div = document.createElement("div");
    div.classList.add("radio-container");

    var input = document.createElement("input");
    input.type = "radio";
    input.name = "markWhenChecked";
    input.value = name;
    input.id = id;
    input.onchange = () => setMarkWhenChecked(name);
    div.appendChild(input);

    // Preserve the selected element when the checkboxes change
    if (name == settings.markWhenChecked) {
      input.checked = true;
    }

    var label = document.createElement("label");
    label.innerHTML = displayName;
    label.htmlFor = id;
    div.appendChild(label);

    container.appendChild(div);
}
createOption("", "None");
for (var checkbox of settings.checkboxes) {
createOption(checkbox, checkbox);
}
}

function updateCheckboxStats(checkbox) {
var checked = getStoredCheckboxRefs(checkbox).size;
var total = pcbdata.footprints.length - pcbdata.bom.skipped.length;
var percent = checked * 100.0 / total;
var td = document.getElementById("checkbox-stats-" + checkbox);
td.firstChild.style.width = percent + "%";
td.lastChild.innerHTML = checked + "/" + total + " (" + Math.round(percent) + "%)";
}

function constrain(number, min, max){
return Math.min(Math.max(parseInt(number), min), max);
}

document.onkeydown = function (e) {
switch (e.key) {
case "n":
if (document.activeElement.type == "text") {
return;
}
if (currentHighlightedRowId !== null) {
checkBomCheckbox(currentHighlightedRowId, "placed");
highlightNextRow();
e.preventDefault();
}
break;
case "ArrowUp":
highlightPreviousRow();
e.preventDefault();
break;
case "ArrowDown":
highlightNextRow();
e.preventDefault();
break;
case "ArrowLeft":
case "ArrowRight":
if (document.activeElement.type != "text"){
e.preventDefault();
let boardRotationElement = document.getElementById("boardRotation")
settings.boardRotation = parseInt(boardRotationElement.value);  // degrees / 5
if (e.key == "ArrowLeft"){
settings.boardRotation += 3;  // 15 degrees
}
else{
settings.boardRotation -= 3;
}
settings.boardRotation = constrain(settings.boardRotation, boardRotationElement.min, boardRotationElement.max);
boardRotationElement.value = settings.boardRotation
setBoardRotation(settings.boardRotation);
}
break;      
default:
break;
}
if (e.altKey) {
switch (e.key) {
case "f":
focusFilterField();
e.preventDefault();
break;
case "r":
focusRefLookupField();
e.preventDefault();
break;
case "z":
changeBomLayout("bom-only");
e.preventDefault();
break;
case "x":
changeBomLayout("left-right");
e.preventDefault();
break;
case "c":
changeBomLayout("top-bottom");
e.preventDefault();
break;
case "v":
changeCanvasLayout("F");
e.preventDefault();
break;
case "b":
changeCanvasLayout("FB");
e.preventDefault();
break;
case "n":
changeCanvasLayout("B");
e.preventDefault();
break;
default:
break;
}
if (e.key >= '1' && e.key <= '9') {
toggleBomCheckbox(currentHighlightedRowId, parseInt(e.key));
e.preventDefault();
}
}
}

function hideNetlistButton() {
document.getElementById("bom-ungrouped-btn").classList.remove("middle-button");
document.getElementById("bom-ungrouped-btn").classList.add("right-most-button");
document.getElementById("bom-netlist-btn").style.display = "none";
}

window.onload = function (e) {
initUtils();
initRender();
initStorage();
initDefaults();
cleanGutters();
populateMetadata();
dbgdiv = document.getElementById("dbg");
bom = document.getElementById("bombody");
bomhead = document.getElementById("bomhead");
filter = "";
reflookup = "";
if (!("nets" in pcbdata)) {
hideNetlistButton();
}
initDone = true;
setBomCheckboxes(document.getElementById("bomCheckboxes").value);
// Triggers render
changeBomLayout(settings.bomlayout);

// Users may leave fullscreen without touching the checkbox. Uncheck.
document.addEventListener('fullscreenchange', () => {
if (!document.fullscreenElement)
document.getElementById('fullscreenCheckbox').checked = false;
});
}

window.onresize = resizeAll;
window.matchMedia("print").addListener(resizeAll);

///////////////////////////////////////////////

///////////////////////////////////////////////

///////////////////////////////////////////////
</script>
</head>

<body>

<div id="topmostdiv" class="topmostdiv">
  <div id="top">
    <div style="float: right; height: 100%;">
      <div class="hideonprint menu" style="float: right; top: 8px;">
        <button class="menubtn"></button>
        <div class="menu-content">
          <label class="menu-label menu-label-top" style="width: calc(50% - 18px)">
            <input id="darkmodeCheckbox" type="checkbox" onchange="setDarkMode(this.checked)">
            Dark mode
          </label><!-- This comment eats space! All of it!
          --><label class="menu-label menu-label-top" style="width: calc(50% - 17px); border-left: 0;">
            <input id="fullscreenCheckbox" type="checkbox" onchange="setFullscreen(this.checked)">
            Full Screen
          </label>
          <label class="menu-label" style="width: calc(50% - 18px)">
            <input id="fabricationCheckbox" type="checkbox" checked onchange="fabricationVisible(this.checked)">
            Fab layer
          </label><!-- This comment eats space! All of it!
          --><label class="menu-label" style="width: calc(50% - 17px); border-left: 0;">
            <input id="silkscreenCheckbox" type="checkbox" checked onchange="silkscreenVisible(this.checked)">
            Silkscreen
          </label>
          <label class="menu-label" style="width: calc(50% - 18px)">
            <input id="referencesCheckbox" type="checkbox" checked onchange="referencesVisible(this.checked)">
            References
          </label><!-- This comment eats space! All of it!
          --><label class="menu-label" style="width: calc(50% - 17px); border-left: 0;">
            <input id="valuesCheckbox" type="checkbox" checked onchange="valuesVisible(this.checked)">
            Values
          </label>
          <div id="tracksAndZonesCheckboxes">
            <label class="menu-label" style="width: calc(50% - 18px)">
              <input id="tracksCheckbox" type="checkbox" checked onchange="tracksVisible(this.checked)">
              Tracks
            </label><!-- This comment eats space! All of it!
            --><label class="menu-label" style="width: calc(50% - 17px); border-left: 0;">
              <input id="zonesCheckbox" type="checkbox" checked onchange="zonesVisible(this.checked)">
              Zones
            </label>
          </div>
          <label class="menu-label" style="width: calc(50% - 18px)">
            <input id="padsCheckbox" type="checkbox" checked onchange="padsVisible(this.checked)">
            Pads
          </label><!-- This comment eats space! All of it!
          --><label class="menu-label" style="width: calc(50% - 17px); border-left: 0;">
            <input id="dnpOutlineCheckbox" type="checkbox" checked onchange="dnpOutline(this.checked)">
            DNP outlined
          </label>
          <label class="menu-label">
            <input id="highlightpin1Checkbox" type="checkbox" onchange="setHighlightPin1(this.checked)">
            Highlight first pin
          </label>
          <label class="menu-label">
            <input id="dragCheckbox" type="checkbox" checked onchange="setRedrawOnDrag(this.checked)">
            Continuous redraw on drag
          </label>
          <label class="menu-label">
            <span>Board rotation</span>
            <span style="float: right"><span id="rotationDegree">0</span>&#176;</span>
            <input id="boardRotation" type="range" min="-36" max="36" value="0" class="slider" oninput="setBoardRotation(this.value)">
          </label>
          <label class="menu-label">
            <div style="margin-left: 5px">Bom checkboxes</div>
            <input id="bomCheckboxes" class="menu-textbox" type=text
                   oninput="setBomCheckboxes(this.value)">
          </label>
          <label class="menu-label">
            <div style="margin-left: 5px">Mark when checked</div>
            <div id="markWhenCheckedContainer"></div>
          </label>
          <label class="menu-label">
            <span class="shameless-plug">
              <span>Created using</span>
              <a id="github-link" target="blank" href="https://github.com/openscopeproject/InteractiveHtmlBom">InteractiveHtmlBom</a>
              <a target="blank" title="Mouse and keyboard help" href="https://github.com/openscopeproject/InteractiveHtmlBom/wiki/Usage#bom-page-mouse-actions" style="text-decoration: none;"><label class="help-link">?</label></a>
            </span>
          </label>
        </div>
      </div>
      <div class="button-container hideonprint"
           style="float: right; position: relative; top: 8px">
        <button id="fl-btn" class="left-most-button" onclick="changeCanvasLayout('F')"
                title="Front only">F
        </button>
        <button id="fb-btn" class="middle-button" onclick="changeCanvasLayout('FB')"
                title="Front and Back">FB
        </button>
        <button id="bl-btn" class="right-most-button" onclick="changeCanvasLayout('B')"
                title="Back only">B
        </button>
      </div>
      <div class="button-container hideonprint"
           style="float: right; position: relative; top: 8px">
        <button id="bom-btn" class="left-most-button" onclick="changeBomLayout('bom-only')"
                title="BOM only"></button>
        <button id="lr-btn" class="middle-button" onclick="changeBomLayout('left-right')"
                title="BOM left, drawings right"></button>
        <button id="tb-btn" class="right-most-button" onclick="changeBomLayout('top-bottom')"
                title="BOM top, drawings bot"></button>
      </div>
      <div class="button-container hideonprint"
           style="float: right; position: relative; top: 8px">
        <button id="bom-grouped-btn" class="left-most-button" onclick="changeBomMode('grouped')"
                title="Grouped BOM"></button>
        <button id="bom-ungrouped-btn" class="middle-button" onclick="changeBomMode('ungrouped')"
                title="Ungrouped BOM"></button>
        <button id="bom-netlist-btn" class="right-most-button" onclick="changeBomMode('netlist')"
                title="Netlist"></button>
      </div>
      <div class="hideonprint menu" style="float: right; top: 8px;">
        <button class="statsbtn"></button>
        <div class="menu-content">
          <table class="stats">
            <tbody>
              <tr>
                <td width="40%">Board stats</td>
                <td>Front</td>
                <td>Back</td>
                <td>Total</td>
              </tr>
              <tr>
                <td>Components</td>
                <td id="stats-components-front">~</td>
                <td id="stats-components-back">~</td>
                <td id="stats-components-total">~</td>
              </tr>
              <tr>
                <td>Groups</td>
                <td id="stats-groups-front">~</td>
                <td id="stats-groups-back">~</td>
                <td id="stats-groups-total">~</td>
              </tr>
              <tr>
                <td>SMD pads</td>
                <td id="stats-smd-pads-front">~</td>
                <td id="stats-smd-pads-back">~</td>
                <td id="stats-smd-pads-total">~</td>
              </tr>
              <tr>
                <td>TH pads</td>
                <td colspan=3 id="stats-th-pads">~</td>
              </tr>
            </tbody>
          </table>
          <table class="stats">
            <col width="40%"/><col />
            <tbody id="checkbox-stats">
              <tr>
                <td colspan=2 style="border-top: 0">Checkboxes</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
      <div class="hideonprint menu" style="float: right; top: 8px;">
        <button class="iobtn"></button>
        <div class="menu-content">
          <div class="menu-label menu-label-top">
            <div style="margin-left: 5px;">Save board image</div>
            <div class="flexbox">
              <input id="render-save-width" class="menu-textbox" type="text" value="1000" placeholder="Width"
                  style="flex-grow: 1; width: 50px;" oninput="validateSaveImgDimension(this)">
              <span>X</span>
              <input id="render-save-height" class="menu-textbox" type="text" value="1000" placeholder="Height"
                  style="flex-grow: 1; width: 50px;" oninput="validateSaveImgDimension(this)">
            </div>
            <label>
              <input id="render-save-transparent" type="checkbox">
              Transparent background
            </label>
            <div class="flexbox">
              <button class="savebtn" onclick="saveImage('F')">Front</button>
              <button class="savebtn" onclick="saveImage('B')">Back</button>
            </div>
          </div>
          <div class="menu-label">
            <span style="margin-left: 5px;">Config and checkbox state</span>
            <div class="flexbox">
              <button class="savebtn" onclick="saveSettings()">Export</button>
              <button class="savebtn" onclick="loadSettings()">Import</button>
            </div>
          </div>
          <div class="menu-label">
            <span style="margin-left: 5px;">Save bom table as</span>
            <div class="flexbox">
              <button class="savebtn" onclick="saveBomTable('csv')">csv</button>
              <button class="savebtn" onclick="saveBomTable('txt')">txt</button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div id="fileinfodiv" style="overflow: auto;">
      <table class="fileinfo">
        <tbody>
          <tr>
            <td id="title" class="title" style="width: 70%">
              Title
            </td>
            <td id="revision" class="title" style="width: 30%">
              Revision
            </td>
          </tr>
          <tr>
            <td id="company">
              Company
            </td>
            <td id="filedate">
              Date
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <div id="bot" class="split" style="height: calc(100% - 80px)">
    <div id="bomdiv" class="split split-horizontal">
      <div style="width: 100%">
        <input id="reflookup" class="textbox searchbox reflookup hideonprint" type="text" placeholder="Ref lookup"
               oninput="updateRefLookup(this.value)">
        <input id="filter" class="textbox searchbox filter hideonprint" type="text" placeholder="Filter"
               oninput="updateFilter(this.value)">
        <div class="button-container hideonprint" style="float: left; margin: 0;">
          <button id="copy" title="Copy bom table to clipboard"
               onclick="saveBomTable('clipboard')"></button>
        </div>
      </div>
      <div id="dbg"></div>
      <table class="bom" id="bomtable">
        <thead id="bomhead">
        </thead>
        <tbody id="bombody">
        </tbody>
      </table>
    </div>
    <div id="canvasdiv" class="split split-horizontal">
      <div id="frontcanvas" class="split" touch-action="none" style="overflow: hidden">
        <div style="position: relative; width: 100%; height: 100%;">
          <canvas id="F_bg" style="position: absolute; left: 0; top: 0; z-index: 0;"></canvas>
          <canvas id="F_fab" style="position: absolute; left: 0; top: 0; z-index: 1;"></canvas>
          <canvas id="F_slk" style="position: absolute; left: 0; top: 0; z-index: 2;"></canvas>
          <canvas id="F_hl" style="position: absolute; left: 0; top: 0; z-index: 3;"></canvas>
        </div>
      </div>
      <div id="backcanvas" class="split" touch-action="none" style="overflow: hidden">
        <div style="position: relative; width: 100%; height: 100%;">
          <canvas id="B_bg" style="position: absolute; left: 0; top: 0; z-index: 0;"></canvas>
          <canvas id="B_fab" style="position: absolute; left: 0; top: 0; z-index: 1;"></canvas>
          <canvas id="B_slk" style="position: absolute; left: 0; top: 0; z-index: 2;"></canvas>
          <canvas id="B_hl" style="position: absolute; left: 0; top: 0; z-index: 3;"></canvas>
        </div>
      </div>
    </div>
  </div>
</div>

</body>

</html>






