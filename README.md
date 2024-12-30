// ==UserScript==
// @name         BLS Spain Morocco Auto Form
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Auto-fill BLS form for Casablanca appointment
// @author       You
// @match        https://www.blsspainmorocco.net/mar/home/index*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=blsspainmorocco.net
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Wait for the page to load
    window.addEventListener('load', () => {
        // User info
        const username = "yahyamohcine@icloud.com";
        const password = "jaghdsjyquecilw";
        const location = "Casablanca";
        const visaType = "casa1";
        const visaSubType = "casa1";
        const category = "normal";
        const appointmentFor = "family";
        const numberOfMembers = "3";

        // Fill username and password
        document.querySelector('input[name="txtEmailId"]').value = username;
        document.querySelector('input[name="txtPwd"]').value = password;

        // Click login button
        document.querySelector('input[name="btnSubmit"]').click();

        // Wait for the next page to load
        setTimeout(() => {
            // Fill the form fields
            document.querySelector('#ddlLocation').value = location;
            document.querySelector('#ddlVisaType').value = visaType;
            document.querySelector('#ddlVisaSubType').value = visaSubType;
            document.querySelector('#ddlCategory').value = category;
            document.querySelector('#ddlAppointmentFor').value = appointmentFor;
            document.querySelector('#txtNoOfMembers').value = numberOfMembers;

            // Submit the form
            document.querySelector('#btnSubmitForm').click();
        }, 5000); // Adjust this delay as needed
    });
})();
