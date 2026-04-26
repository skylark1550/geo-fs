// ==UserScript==
// @name         GeoFS Minimap
// @version      0.1.2
// @description  Adds the minimap from MSFS2024
// @author       GGamerGGuy
// @match        https://geo-fs.com/geofs.php*
// @match        https://*.geo-fs.com/geofs.php*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=geo-fs.com
// @grant        none
// @downloadURL  https://github.com/tylerbmusic/GeoFS-Minimap/raw/refs/heads/main/userscript.js
// @updateURL    https://github.com/tylerbmusic/GeoFS-Minimap/raw/refs/heads/main/userscript.js
// ==/UserScript==
function mmWait() {
    if (window.geofs.cautiousWithTerrain == false) {
        setTimeout(() => {
            window.mapInit();
        }, 1000);
    } else {
        setTimeout(() => {
            mmWait();
        }, 1000);
    }
};
(function() {
    'use strict';
    if (!window.gmenu || !window.GMenu) {
        fetch(
            "https://raw.githubusercontent.com/tylerbmusic/GeoFS-Addon-Menu/refs/heads/main/addonMenu.js"
        )
            .then((response) => response.text())
            .then((script) => {
            eval(script);
        })
            .then(() => {
            setTimeout(afterGMenu, 100);
        });
    } else afterGMenu()

    function afterGMenu() {
        const mapM = new window.GMenu("Minimap", "mm");
        mapM.addItem('Heading Up: ', 'HdgUp', 'checkbox', 0, 'false');
        mapM.addItem('Feet per zoom level: ', 'ZoomSpace', 'number', 0, '3000');
        mmWait();
    }
})();
window.mapInit = function() {
    var h = document.createElement('div');
    let html = `<div id="hdgTBox" style="display: none;color: white;text-align: center;position: fixed;left: 10px;right: 0;height: 30px;width: 100px;top: 10px;backdrop-filter: blur(10px);z-index: 21;background: rgba(0,0,0,0.1);border: 1px solid lightgray;"><div style="background: #00C8FF;width: 10%;height: 100%;position: absolute;z-index: 5001;"></div><div id="hdgText" style="padding: 5.5px;font-family: 'Roboto';font-size: 16px;">HDG 360-</div></div>`;
    document.body.appendChild(h);
    h.className = "minimap";
    h.innerHTML = html;

    var c = document.createElement('div');
    html = `<div style="display: none; color: white;text-align: center;position: fixed;left: 173px;right: 0;height: 30px;width: 100px;top: 10px;backdrop-filter: blur(10px);z-index: 21;background: rgba(0,0,0,0.1);border: 1px solid lightgray;display: block;" id="crsTBox"><div style="background: #FF00FF;width: 10%;height: 100%;position: absolute;z-index: 5001;"></div><div style="padding: 5.5px;font-family: 'Roboto';font-size: 16px;" id="crsText">CRS 360-</div></div>`;
    document.body.appendChild(c);
    c.className = "minimap";
    c.innerHTML = html;

    var m = document.createElement('div');
    m.style.position = 'fixed';
    m.style.borderRadius = '200px';
    m.style.backdropFilter = 'blur(10px)';
    m.style.background = '#00000048';
    m.style.border = '2px solid gray';
    m.style.top = "40px";
    m.style.left = "40px";
    document.body.appendChild(m);
    html = `<div style="color: white;text-align: center;position: fixed;left: 0;padding-left: 10%;padding-right: 10%;top: -20%;right: 0;margin: 5% auto;"><div style="padding: 0px 10px 0px 10px;background: #111;width: 20%;margin: auto;text-align: center;" id="hdgNum">0°</div></div>
    <svg xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape" xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd" xmlns="http://www.w3.org/2000/svg" xmlns:svg="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 5.2916665 5.2916666" version="1.1" id="svg1" inkscape:version="1.4 (86a8ad7, 2024-10-11)" sodipodi:docname="arrowDown.svg" style="position: fixed;top: -8%;left: 45%;"><sodipodi:namedview id="namedview1" pagecolor="#ffffff" bordercolor="#000000" borderopacity="0.25" inkscape:showpageshadow="2" inkscape:pageopacity="0.0" inkscape:pagecheckerboard="0" inkscape:deskcolor="#d1d1d1" inkscape:document-units="mm" showgrid="true" inkscape:zoom="31.163807" inkscape:cx="4.0271075" inkscape:cy="8.7441179" inkscape:window-width="1920" inkscape:window-height="991" inkscape:window-x="-9" inkscape:window-y="-9" inkscape:window-maximized="1" inkscape:current-layer="layer1"><inkscape:grid id="grid1" units="px" originx="0" originy="0" spacingx="0.26458332" spacingy="0.26458332" empcolor="#0099e5" empopacity="0.30196078" color="#0099e5" opacity="0.14901961" empspacing="5" enabled="true" visible="true"></inkscape:grid></sodipodi:namedview><defs id="defs1"><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter12" x="-0.4535433" y="-0.52370672" width="1.9070866" height="2.0474134"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood11"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="0.500000" id="feGaussianBlur11"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset11"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite11"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite12"></feComposite></filter></defs><g inkscape:label="Layer 1" inkscape:groupmode="layer" id="layer1"><path style="fill:#ffffff;fill-opacity:1;stroke-width:0.264999;filter:url(#filter12)" d="M 1.3229166,1.3229166 2.6458332,3.6142754 3.96875,1.3229166 Z" id="path1"></path></g></svg>
    <div id="map" style="position: relative;width: 200px;height: 200px; border-radius: 200px; z-index: 0"></div>
    <div style="position: fixed;width: 200px;height: 200px;background-image: url(&quot;images/instruments/compass-grad.png&quot;);background-repeat: no-repeat;background-size: 100%;top: 0; filter: drop-shadow(0px 0px 2px #000000aa);" id="mCompass"></div>
    <div style="position: fixed;width: 200px;height: 200px;background-image: url(&quot;https://tylerbmusic.github.io/GPWS-files_geofs/hdgBug.svg&quot;);background-repeat: no-repeat;background-size: 100%;top: 0px;rotate: 0deg; display: none;" id="hdgBug"></div>
    <div style="position: fixed;width: 200px;height: 200px;background-image: url(&quot;https://tylerbmusic.github.io/GPWS-files_geofs/crsArrow.svg&quot;);background-repeat: no-repeat;background-size: 100%;top: 0px;rotate: 0deg; display: none;" id="crsArrow"></div>
    <div style="position: fixed;width: 200px;height: 200px;top: 0px;display: none;" id="mmCDI"><svg xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape" xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd" xmlns="http://www.w3.org/2000/svg" xmlns:svg="http://www.w3.org/2000/svg" width="200" height="200" viewBox="0 0 52.916667 52.916666" version="1.1" id="svg1" inkscape:version="1.4 (86a8ad7, 2024-10-11)" sodipodi:docname="CDI.svg"><sodipodi:namedview id="namedview1" pagecolor="#ffffff" bordercolor="#000000" borderopacity="0.25" inkscape:showpageshadow="2" inkscape:pageopacity="0.0" inkscape:pagecheckerboard="true" inkscape:deskcolor="#d1d1d1" inkscape:document-units="mm" showgrid="true" inkscape:zoom="4" inkscape:cx="78.375" inkscape:cy="125.375" inkscape:window-width="1920" inkscape:window-height="991" inkscape:window-x="-9" inkscape:window-y="-9" inkscape:window-maximized="1" inkscape:current-layer="layer2"><inkscape:grid id="grid3" units="px" originx="0" originy="0" spacingx="1.3229167" spacingy="1.3229168" empcolor="#0099e5" empopacity="0.30196078" color="#0099e5" opacity="0.14901961" empspacing="5" enabled="true" visible="true"></inkscape:grid></sodipodi:namedview><defs id="defs1"><inkscape:path-effect effect="fillet_chamfer" id="path-effect5" is_visible="true" lpeversion="1" nodesatellites_param="F,0,0,1,0,0,0,1 @ F,0,1,1,0,0.021962011,0,1 @ F,0,1,1,0,0.021962011,0,1 @ F,0,0,1,0,0.021962011,0,1 @ F,0,1,1,0,0.021962011,0,1 @ F,0,1,1,0,0.021962011,0,1 @ F,0,0,1,0,0,0,1" radius="0" unit="px" method="auto" mode="F" chamfer_steps="1" flexible="false" use_knot_distance="true" apply_no_radius="true" apply_with_radius="true" only_selected="false" hide_knots="false"></inkscape:path-effect><inkscape:path-effect effect="fillet_chamfer" id="path-effect4" is_visible="true" lpeversion="1" nodesatellites_param="F,0,1,1,0,0.25410949,0,1 @ F,0,0,1,0,0.25410949,0,1 @ F,0,1,1,0,0.25410949,0,1" radius="0" unit="px" method="auto" mode="F" chamfer_steps="1" flexible="false" use_knot_distance="true" apply_no_radius="true" apply_with_radius="true" only_selected="false" hide_knots="false"></inkscape:path-effect><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter30" x="-0.50362183" y="-0.50362183" width="2.0072437" height="2.0072437"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood29"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="0.500000" id="feGaussianBlur29"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset29"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite29"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite30"></feComposite></filter><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter34" x="-0.50362183" y="-0.50362183" width="2.0072437" height="2.0072437"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood33"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="0.500000" id="feGaussianBlur33"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset33"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite33"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite34"></feComposite></filter><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter36" x="-0.50362183" y="-0.50362183" width="2.0072437" height="2.0072437"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood34"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="0.500000" id="feGaussianBlur34"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset34"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite35"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite36"></feComposite></filter><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter38" x="-0.50362183" y="-0.50362183" width="2.0072437" height="2.0072437"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood36"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="0.500000" id="feGaussianBlur36"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset36"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite37"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite38"></feComposite></filter><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter41" x="-0.455759" y="-0.22696673" width="1.911518" height="1.4539335"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood40"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="1.000000" id="feGaussianBlur40"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset40"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite40"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite41"></feComposite></filter><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter44" x="-3.6283492" y="-0.22677166" width="8.2566984" height="1.4535433"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood43"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="1.000000" id="feGaussianBlur43"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset43"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite43"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite44"></feComposite></filter><filter style="color-interpolation-filters:sRGB;" inkscape:label="Drop Shadow" id="filter47" x="-3.6283551" y="-0.090708659" width="8.2567101" height="1.1814173"><feFlood result="flood" in="SourceGraphic" flood-opacity="0.501961" flood-color="rgb(0,0,0)" id="feFlood46"></feFlood><feGaussianBlur result="blur" in="SourceGraphic" stdDeviation="1.000000" id="feGaussianBlur46"></feGaussianBlur><feOffset result="offset" in="blur" dx="0.000000" dy="0.000000" id="feOffset46"></feOffset><feComposite result="comp1" operator="in" in="flood" in2="offset" id="feComposite46"></feComposite><feComposite result="comp2" operator="over" in="SourceGraphic" in2="comp1" id="feComposite47"></feComposite></filter></defs><g inkscape:label="CDI BG" inkscape:groupmode="layer" id="layer1"><path style="fill:#ff00ff;stroke-width:0.264583;filter:url(#filter41)" d="M 26.127603,13.229166 V 5.3136283 a 0.02196201,0.02196201 44.999996 0 0 -0.02196,-0.021962 l -2.27118,3e-7 a 0.00909696,0.00909696 67.499994 0 1 -0.0064,-0.01553 l 2.614775,-2.6147744 a 0.02196201,0.02196201 179.99999 0 1 0.03106,0 l 2.614776,2.6147744 a 0.00909696,0.00909696 112.5 0 1 -0.0064,0.01553 l -2.271182,-3e-7 a 0.02196201,0.02196201 135 0 0 -0.02196,0.021962 v 7.9155377 z" id="path4" inkscape:path-effect="#path-effect5" inkscape:original-d="M 26.127603,13.229166 V 5.2916663 l -2.315104,3e-7 2.645833,-2.6458334 2.645834,2.6458334 -2.315106,-3e-7 v 7.9374997 z"></path><circle style="fill:#ff00ff;fill-opacity:0;stroke:#ffffff;stroke-width:0.264999;stroke-dasharray:none;stroke-opacity:1;filter:url(#filter38)" id="path6" cx="13.229168" cy="26.458336" r="1.3229167"></circle><circle style="fill:#ff00ff;fill-opacity:0;stroke:#ffffff;stroke-width:0.264999;stroke-dasharray:none;stroke-opacity:1;filter:url(#filter36)" id="path7" cx="19.843752" cy="26.458336" r="1.3229167"></circle><circle style="fill:#ff00ff;fill-opacity:0;stroke:#ffffff;stroke-width:0.264999;stroke-dasharray:none;stroke-opacity:1;filter:url(#filter34)" id="path8" cx="33.072918" cy="26.458336" r="1.3229167"></circle><circle style="fill:#ff00ff;fill-opacity:0;stroke:#ffffff;stroke-width:0.264999;stroke-dasharray:none;stroke-opacity:1;filter:url(#filter30)" id="path9" cx="39.687504" cy="26.458336" r="1.3229167"></circle><rect style="fill:#ff00ff;fill-opacity:1;stroke:none;stroke-width:0.264999;stroke-dasharray:none;stroke-opacity:1;filter:url(#filter44)" id="rect9" width="0.66145784" height="10.583333" x="26.127602" y="39.6875" ry="0.33072892"></rect><rect style="fill:#ff00ff;fill-opacity:1;stroke:none;stroke-width:0.2095;stroke-dasharray:none;stroke-opacity:1" id="rect10" width="0.66145784" height="6.6145873" x="26.127602" y="39.6875"></rect></g><g inkscape:groupmode="layer" id="cdi-moveable" inkscape:label="CDI slider" style="mix-blend-mode:normal"><rect style="fill:#ff00ff;stroke-width:0.264583;filter:url(#filter47)" id="rect3" width="0.66145676" height="26.458334" x="26.127604" y="13.229166" ry="0.22921467" rx="0"></rect></g></svg></div>
    <svg id="plen" xmlns="http://www.w3.org/2000/svg" height="48px" viewBox="0 -960 960 960" width="48px" fill="#ffffff" style="position: fixed;top: 0px;left: 0px;margin: 38%;filter: drop-shadow(0px 0px 2px black);"><path d="M319-132v-45l113-80v-190L132-325v-61l300-212v-182q0-20 14-34t34-14q20 0 34 14t14 34v182l300 212v61L528-447v190l112 80v45l-160-50-161 50Z"></path></svg>`;
    m.className = "minimap";
    m.innerHTML = html;

    window.theMap = window.L.map('map').setView([51.505, -0.09], 13);
    window.L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(window.theMap);
    window.theMap.zoomControl._container.remove();
    window.theMap.attributionControl._container.remove();
    window.mapUpdate();
}
window.mapUpdate = function() {
    let d = document.getElementsByClassName("minimap");
    for (var i in d) {
        if (d[i].style) {
            d[i].style.display = (window.instruments.visible) ? "block" : "none";
        }
    }
    //position and rotation
    var ldgAGL = (window.geofs.animation.values.altitude !== undefined && window.geofs.animation.values.groundElevationFeet !== undefined) ? ((window.geofs.animation.values.altitude - window.geofs.animation.values.groundElevationFeet) + (window.geofs.aircraft.instance.collisionPoints[window.geofs.aircraft.instance.collisionPoints.length - 2].worldPosition[2]*3.2808399)) : 'N/A'; //Get the true height above the ground
    if (ldgAGL != "N/A") {
        var ll = window.geofs.aircraft.instance.llaLocation;
        window.theMap.setView([ll[0], ll[1]], Math.ceil(16-(ldgAGL/Number(localStorage.getItem("mmZoomSpace")))));
        document.getElementById("hdgNum").innerHTML = Math.round(window.geofs.animation.values.heading360) + "°";
        if (localStorage.getItem("mmHdgUp") == "true") {
            document.getElementById("mCompass").style.rotate = -window.geofs.animation.values.heading360 + "deg";
            document.getElementById("map").style.rotate = -window.geofs.animation.values.heading360 + "deg";
            document.getElementById("plen").style.rotate = "0deg";

            if (window.geofs.nav.currentNAVUnit && (window.geofs.nav.currentNAVUnit.bearing !== 0)) {
                let crs = window.geofs.nav.currentNAVUnit.course;
                let brg = window.geofs.animation.values.heading360 - window.geofs.nav.currentNAVUnit.bearingToStation;
                let crsDev = Math.max(-15, Math.min(window.geofs.nav.currentNAVUnit.courseDeviation*5, 15));
                document.getElementById("crsTBox").style.display = "block";
                document.getElementById("crsText").innerHTML = `BRG ${Math.round(brg) % 360}°`;
                let a = document.getElementById("crsArrow");
                a.style.display = "block";
                a.style.rotate = (brg - window.geofs.animation.values.heading360) + "deg";
                let c = document.getElementById("mmCDI");
                c.style.display = "block";
                c.style.rotate = window.geofs.nav.currentNAVUnit.direction == 'from' ? ((crs - window.geofs.animation.values.heading360 + 180) % 360) + "deg" : (crs - window.geofs.animation.values.heading360) + "deg";
                document.getElementById("cdi-moveable").style.translate = crsDev + "px";
            } else {
                document.getElementById("crsTBox").style.display = "none";
                document.getElementById("crsArrow").display = "none";
                document.getElementById("mmCDI").style.display = "none";
            }
            if (typeof window.geofs.nav.HDG == 'number') {
                document.getElementById("hdgTBox").style.display = "block";
                document.getElementById("hdgText").innerHTML = `HDG ${Math.round(window.geofs.nav.HDG) % 360}°`;
                let a = document.getElementById("hdgBug");
                a.style.display = "block";
                a.style.rotate = (window.geofs.nav.HDG - window.geofs.animation.values.heading360) + "deg";
            } else {
                document.getElementById("hdgTBox").style.display = "none";
                let a = document.getElementById("hdgBug");
                a.style.display = "none";
            }
        } else {
            document.getElementById("mCompass").style.rotate = "0deg";
            document.getElementById("map").style.rotate = "0deg";
            document.getElementById("plen").style.rotate = window.geofs.animation.values.heading360 + "deg";
            if (window.geofs.nav.currentNAVUnit && (window.geofs.nav.currentNAVUnit.bearing !== 0)) {
                let crs = window.geofs.nav.currentNAVUnit.course;
                let brg = window.geofs.animation.values.heading360 - window.geofs.nav.currentNAVUnit.bearingToStation;
                let crsDev = Math.max(-15, Math.min(window.geofs.nav.currentNAVUnit.courseDeviation*5, 15));
                document.getElementById("crsTBox").style.display = "block";
                document.getElementById("crsText").innerHTML = `BRG ${Math.round(brg) % 360}°`;
                let a = document.getElementById("crsArrow");
                a.style.display = "block";
                a.style.rotate = (brg) + "deg";
                let c = document.getElementById("mmCDI");
                c.style.display = "block";
                c.style.rotate = window.geofs.nav.currentNAVUnit.direction == 'from' ? ((crs + 180) % 360) + "deg" : (crs) + "deg";
                document.getElementById("cdi-moveable").style.translate = crsDev + "px";
            } else {
                document.getElementById("crsTBox").style.display = "none";
                document.getElementById("crsArrow").display = "none";
                document.getElementById("mmCDI").style.display = "none";
            }
            if (window.geofs.nav.HDG) {
                document.getElementById("hdgTBox").style.display = "block";
                document.getElementById("hdgText").innerHTML = `HDG ${Math.round(window.geofs.nav.HDG) % 360}°`;
                let a = document.getElementById("hdgBug");
                a.style.display = "block";
                a.style.rotate = (window.geofs.nav.HDG) + "deg";
            } else {
                document.getElementById("hdgTBox").style.display = "none";
                let a = document.getElementById("hdgBug");
                a.style.display = "none";
            }
        }
    }
    setTimeout(window.mapUpdate, 40);
}
