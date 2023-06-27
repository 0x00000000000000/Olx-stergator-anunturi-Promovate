// ==UserScript==
// @name         Remove elements with "adCard-featured" on olx.ro (Sterge anunturile promovate pe Olx ROMANIA, vezi exeomplu in descriere)
// @namespace    olxro-remove-adCard-featured
// @version      1.0
// @description  Removes elements with "adCard-featured" on olx.ro
// @author       BAGHERA ROMANIA
// @match        https://www.olx.ro/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Function to remove "promovat" banners and their parent divs
    function removeBanners() {
        let banners = document.querySelectorAll('[data-testid="adCard-featured"]');
        banners.forEach(banner => {
            let parentDiv = banner.closest('[data-cy="l-card"]');
            if (parentDiv) {
                parentDiv.remove();
            }
        });
    }

    // Run the function once the page has fully loaded
    window.addEventListener('load', removeBanners);

    // Observe changes to the page <body> and run the function again if changes are detected
    let observer = new MutationObserver(removeBanners);
    observer.observe(document.body, {childList: true, subtree: true});
})();
