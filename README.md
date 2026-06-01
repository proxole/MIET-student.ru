<html lang="ru"><head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MIET College</title>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<script>
function openSchedule() {
    window.open("https://www.miet.ru/schedule", "_blank");
}
</script>

<style>
/* ========== ОСНОВНЫЕ СТИЛИ ========== */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f4f6f9;
    scroll-behavior: smooth;
}

/* HEADER */
header {
    background: #1e2a38;
    color: white;
    padding: 15px 30px;
    animation: slideDown 0.6s ease;
}

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.menu-list {
    list-style: none;
    display: flex;
    gap: 20px;
}

.menu-link {
    color: white;
    text-decoration: none;
    transition: 0.3s;
}

.menu-link:hover {
    color: #3b82f6;
}

/* HERO */
.hero {
    text-align: center;
    padding: 80px 20px;
    background: linear-gradient(135deg, #3b82f6, #6366f1);
    color: white;
    animation: fadeIn 1s ease;
}

/* CONTENT */
.container {
    max-width: 1000px;
    margin: auto;
    padding: 20px;
}

.card {
    background: white;
    padding: 20px;
    margin: 20px 0;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    transform: translateY(40px);
    opacity: 0;
    animation: riseUp 0.8s ease forwards;
}

.card a {
    text-decoration: none;
    color: #1e40af;
}

.card a:hover {
    color: #3b82f6;
    text-decoration: underline;
}

.info {
    text-align: center;
    margin-top: 30px;
    font-size: 18px;
}

/* ANIMATIONS */
@keyframes fadeIn {
    from {opacity: 0;}
    to {opacity: 1;}
}

@keyframes slideDown {
    from {transform: translateY(-100%);}
    to {transform: translateY(0);}
}

@keyframes riseUp {
    to {
        transform: translateY(0);
        opacity: 1;
    }
}

/* CALENDAR */
.calendar-container {
    position: relative;
}

.calendar-crop {
    height: 420px;
    overflow: hidden;
    border-radius: 10px;
}

.calendar-crop iframe {
    height: 500px;
    margin-top: -5px;
}

.calendar-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
}

.calendar-title {
    background: #1e2a38;
    color: white;
    padding: 12px;
    text-align: center;
    font-weight: 600;
    cursor: pointer;
}

.logo-link {
    display: flex;
    align-items: center;
    transition: 0.3s;
}

.logo-link:hover {
    transform: scale(1.02);
    opacity: 0.9;
}

/* ПРАЗДНИКИ */
.holidays-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.holiday-item {
    display: flex;
    align-items: center;
    gap: 15px;
    padding: 12px;
    background: linear-gradient(135deg, #fff 0%, #fefce8 100%);
    border-radius: 12px;
    transition: transform 0.2s, box-shadow 0.2s;
    border-left: 4px solid;
}

.holiday-item:hover {
    transform: translateX(5px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
}

.holiday-item.federal { border-left-color: #dc2626; background: linear-gradient(135deg, #fff 0%, #fef2f2 100%); }
.holiday-item.world { border-left-color: #3b82f6; background: linear-gradient(135deg, #fff 0%, #eff6ff 100%); }
.holiday-item.other { border-left-color: #10b981; background: linear-gradient(135deg, #fff 0%, #ecfdf5 100%); }

.holiday-icon {
    font-size: 32px;
    width: 50px;
    text-align: center;
}

.holiday-content {
    flex: 1;
}

.holiday-name {
    font-weight: bold;
    font-size: 1rem;
    margin-bottom: 4px;
    color: #1e2a38;
}

.holiday-date {
    font-size: 0.8rem;
    color: #6b7280;
    display: inline-block;
    background: rgba(0,0,0,0.05);
    padding: 2px 8px;
    border-radius: 12px;
}

.holiday-description {
    font-size: 0.85rem;
    color: #4b5563;
    margin-top: 5px;
}

.no-holiday {
    text-align: center;
    padding: 30px 20px;
    background: linear-gradient(135deg, #f3f4f6 0%, #e5e7eb 100%);
    border-radius: 12px;
}

.no-holiday-icon {
    font-size: 48px;
    margin-bottom: 10px;
    opacity: 0.5;
}

.no-holiday-text {
    color: #6b7280;
    font-size: 0.95rem;
}

.holiday-tip {
    margin-top: 12px;
    padding-top: 12px;
    border-top: 1px dashed #e5e7eb;
    font-size: 0.75rem;
    color: #9ca3af;
    text-align: center;
}

/* ФАКТЫ */
.fact-content {
    background: linear-gradient(135deg, #e0f2fe 0%, #fae8ff 100%);
    padding: 20px;
    border-radius: 12px;
    font-size: 1rem;
    line-height: 1.5;
    color: #1e2a38;
    min-height: 80px;
    display: flex;
    align-items: center;
    gap: 8px;
    flex-wrap: wrap;
}

#fact-text {
    flex: 1;
}

.fact-button {
    margin-top: 15px;
    background: none;
    border: 1px solid #e5e7eb;
    border-radius: 20px;
    padding: 5px 15px;
    cursor: pointer;
    font-size: 12px;
}

.fact-button:hover {
    background: #f3f4f6;
    transform: scale(1.02);
    transition: all 0.2s;
}

.loading-state {
    text-align: center;
    padding: 20px;
    color: #6b7280;
}

/* ========== АДАПТАЦИЯ ДЛЯ ТЕЛЕФОНОВ ========== */
@media (max-width: 768px) {
    /* Шапка - сильно уменьшаем логотип */
    header {
        padding: 8px 15px;
    }
    
    .nav {
        flex-direction: column;
        align-items: center;
        gap: 8px;
    }
    
    /* Логотип - сильно уменьшенный */
    .logo-link svg {
        height: 28px !important;
        width: auto !important;
        max-width: 160px;
    }
    
    /* Меню - компактное */
    .menu-list {
        flex-direction: row !important;
        flex-wrap: wrap;
        justify-content: center;
        gap: 12px !important;
        padding: 0;
        margin: 0;
    }
    
    .menu-link {
        font-size: 12px;
        padding: 4px 8px;
    }
    
    /* Герой */
    .hero {
        padding: 30px 15px;
    }
    
    .hero h1 {
        font-size: 20px;
        margin: 0 0 10px 0;
    }
    
    .hero p {
        font-size: 12px;
        margin: 0;
    }
    
    /* Контейнер */
    .container {
        padding: 10px;
    }
    
    /* Карточки */
    .card {
        padding: 12px;
        margin: 12px 0;
    }
    
    .card h3 {
        font-size: 16px;
        margin: 0 0 10px 0;
    }
    
    /* Ссылки материалов - большие кнопки для пальцев */
    .card p {
        display: flex;
        flex-direction: column;
        gap: 8px;
        margin: 0;
    }
    
    .card p a {
        display: block;
        text-align: center;
        padding: 10px;
        background: #f0f2f5;
        border-radius: 8px;
        font-size: 14px;
    }
    
    /* Инфо блок */
    .info {
        margin-top: 15px;
    }
    
    .info h3 {
        font-size: 16px;
    }
    
    .info p {
        font-size: 12px;
    }
    
    /* Календарь */
    .calendar-crop {
        height: 300px;
    }
    
    .calendar-crop iframe {
        height: 380px;
    }
    
    .calendar-title {
        padding: 8px;
        font-size: 12px;
    }
    
    /* Праздники */
    .holiday-item {
        padding: 8px;
        gap: 8px;
    }
    
    .holiday-icon {
        font-size: 24px;
        width: 35px;
    }
    
    .holiday-name {
        font-size: 13px;
    }
    
    .holiday-description {
        font-size: 11px;
    }
    
    .holiday-date {
        font-size: 10px;
        padding: 2px 6px;
        white-space: nowrap;
    }
    
    .no-holiday {
        padding: 20px 15px;
    }
    
    .no-holiday-icon {
        font-size: 36px;
    }
    
    .no-holiday-text {
        font-size: 12px;
    }
    
    .holiday-tip {
        font-size: 11px;
    }
    
    /* Факты */
    .fact-content {
        padding: 12px;
        font-size: 13px;
        min-height: 60px;
    }
    
    .fact-content i {
        font-size: 16px;
    }
    
    .fact-button {
        width: 100%;
        padding: 8px;
        font-size: 12px;
    }
}

/* Для очень маленьких телефонов */
@media (max-width: 480px) {
    .logo-link svg {
        height: 16px !important;
        max-width: 100px;
    }
    
    .menu-link {
        font-size: 10px;
        padding: 3px 6px;
    }
    
    .card p a {
        padding: 8px;
        font-size: 13px;
    }
    
    .holiday-icon {
        font-size: 20px;
        width: 30px;
    }
    
    .holiday-name {
        font-size: 12px;
    }
    
    .holiday-date {
        font-size: 9px;
        white-space: normal;
    }
    
    .holiday-description {
        font-size: 10px;
    }
}
</style>
</head>

<body>

<header>
    <div class="nav">
        <a href="https://miet.ru" target="_blank" class="logo-link">  
            <svg xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:cc="http://creativecommons.org/ns#" xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:svg="http://www.w3.org/2000/svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 876.17749 136.77" height="136.77" width="876.17749" xml:space="preserve" version="1.1" id="svg2"><metadata id="metadata8"><rdf:rdf><cc:work rdf:about=""><dc:format>image/svg+xml</dc:format><dc:type rdf:resource="http://purl.org/dc/dcmitype/StillImage"></dc:type></cc:work></rdf:rdf></metadata><defs id="defs6"><clipPath id="clipPath16" clipPathUnits="userSpaceOnUse"><path id="path18" d="m 0,109.416 700.942,0 L 700.942,0 0,0 0,109.416 Z"></path></clipPath><clipPath id="clipPath198" clipPathUnits="userSpaceOnUse"><path id="path200" d="m 0,109.416 700.942,0 L 700.942,0 0,0 0,109.416 Z"></path></clipPath><clipPath id="clipPath206" clipPathUnits="userSpaceOnUse"><path id="path208" d="m 0.00138855,109.414 109.41161145,0 0,-109.41157385 -109.41161145,0 0,109.41157385 z"></path></clipPath></defs><g transform="matrix(1.25,0,0,-1.25,0,136.77)" id="g10"><g id="g12"><g clip-path="url(#clipPath16)" id="g14"><g transform="translate(204.9558,87.699)" id="g20"><path id="path22" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-66.021 -14.599,0 0,33.661 c 0,6.881 0.093,13.484 0.279,20.086 -1.674,-6.324 -3.254,-12.182 -5.672,-20.086 l -10.135,-33.661 -13.019,0 -10.321,33.661 c -2.325,7.904 -4.371,13.856 -6.045,19.992 0.186,-6.602 0.28,-13.111 0.28,-19.899 l 0,-33.754 -14.414,0 0,66.021 23.526,0 7.904,-25.851 c 2.139,-7.066 4.091,-13.947 5.672,-20.363 1.581,6.508 3.534,13.483 5.58,20.363 L -23.154,0 0,0 Z"></path></g><g transform="translate(274.6048,87.699)" id="g24"><path id="path26" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-66.021 -14.599,0 0,19.62 c 0,10.415 0.186,20.086 0.558,28.454 -3.44,-6.788 -8.09,-14.97 -12.367,-22.41 l -14.692,-25.664 -15.901,0 0,66.021 14.599,0 0,-21.201 c 0,-10.136 -0.186,-18.505 -0.558,-25.85 3.162,6.509 6.881,13.111 10.507,19.341 L -16.366,0 0,0 Z"></path></g><g transform="translate(341.3704,54.9675)" id="g28"><path id="path30" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c 0,-19.993 -12.646,-34.963 -33.475,-34.963 -10.229,0 -18.132,3.44 -26.129,10.972 l 8.647,10.229 c 7.067,-5.672 11.066,-7.905 17.854,-7.905 9.578,0 16.18,6.045 17.853,16.18 l -26.594,0 0,12.647 26.129,0 c -2.139,8.74 -8.368,13.948 -17.481,13.948 -5.858,0 -9.95,-1.488 -16.645,-7.253 l -8.834,10.415 c 7.625,6.788 14.321,10.135 25.2,10.135 C -12.181,34.405 0,19.248 0,0"></path></g><g transform="translate(399.303,74.7737)" id="g32"><path id="path34" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -18.783,0 0,-53.096 -15.065,0 0,53.096 -18.597,0 0,12.925 L 0,12.925 0,0 Z"></path></g><g transform="translate(433.4456,72.6194)" id="g36"><path id="path38" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -2.51,0 0,6.769 -7.296,0 0,-6.769 -2.488,0 0,14.972 2.488,0 0,-6.094 7.296,0 0,6.094 2.51,0 L 0,0 Z"></path></g><g transform="translate(447.0315,78.0598)" id="g40"><path id="path42" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -0.633,1.835 C -1.35,3.922 -2.045,5.841 -2.572,7.634 -3.1,5.841 -3.796,3.901 -4.533,1.813 L -5.166,0 0,0 Z m 0.717,-2.066 -6.6,0 -1.16,-3.374 -2.53,0 5.398,14.972 3.269,0 5.398,-14.972 -2.594,0 -1.181,3.374 z"></path></g><g transform="translate(458.0237,87.5915)" id="g44"><path id="path46" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-12.863 6.917,0 0,12.863 2.488,0 0,-12.863 1.814,0 0,-5.23 -2.426,0 0,3.121 -11.281,0 L -2.488,0 0,0 Z"></path></g><g transform="translate(486.012,87.5915)" id="g48"><path id="path50" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-14.972 -2.425,0 0,5.883 c 0,2.214 0.042,4.323 0.148,6.221 -0.95,-1.708 -2.152,-3.669 -3.374,-5.652 l -4.007,-6.452 -2.678,0 0,14.972 2.425,0 0,-6.073 c 0,-2.236 -0.022,-4.176 -0.127,-5.968 0.949,1.708 2.004,3.5 3.164,5.335 L -2.721,0 0,0 Z"></path></g><g transform="translate(493.1028,80.1057)" id="g52"><path id="path54" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c 0,-3.374 1.877,-5.631 4.724,-5.631 2.847,0 4.703,2.257 4.703,5.631 0,3.353 -1.856,5.63 -4.703,5.63 C 1.877,5.63 0,3.353 0,0 m 11.979,0 c 0,-4.471 -2.743,-7.824 -7.255,-7.824 -4.513,0 -7.275,3.353 -7.275,7.824 0,4.47 2.762,7.823 7.275,7.823 4.512,0 7.255,-3.353 7.255,-7.823"></path></g><g transform="translate(521.9153,72.6194)" id="g56"><path id="path58" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -2.51,0 0,6.769 -7.296,0 0,-6.769 -2.488,0 0,14.972 2.488,0 0,-6.094 7.296,0 0,6.094 2.51,0 L 0,0 Z"></path></g><g transform="translate(535.5013,78.0598)" id="g60"><path id="path62" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -0.633,1.835 C -1.35,3.922 -2.045,5.841 -2.572,7.634 -3.1,5.841 -3.796,3.901 -4.533,1.813 L -5.166,0 0,0 Z m 0.717,-2.066 -6.6,0 -1.16,-3.374 -2.53,0 5.398,14.972 3.269,0 5.398,-14.972 -2.594,0 -1.181,3.374 z"></path></g><g transform="translate(542.8665,72.6614)" id="g64"><path id="path66" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 0.273,2.109 C 0.548,2.046 0.97,2.003 1.307,2.003 c 1.645,0 1.709,1.603 1.729,4.83 l 0.042,8.097 10.481,0 0,-14.972 -2.489,0 0,12.863 -5.651,0 -0.042,-6.41 C 5.355,2.256 4.829,-0.211 1.603,-0.211 1.012,-0.211 0.442,-0.126 0,0"></path></g><g transform="translate(567.8607,74.6858)" id="g68"><path id="path70" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 C 1.771,0 2.931,0.865 2.931,2.573 2.931,4.281 1.771,5.146 0,5.146 l -3.585,0 L -3.585,0 0,0 Z m -6.073,12.906 2.488,0 0,-5.694 3.985,0 c 2.974,0 5.019,-1.75 5.019,-4.639 0,-2.91 -2.045,-4.639 -5.019,-4.639 l -6.473,0 0,14.972 z"></path></g><g transform="translate(589.9232,72.6194)" id="g72"><path id="path74" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -2.51,0 0,6.769 -7.296,0 0,-6.769 -2.488,0 0,14.972 2.488,0 0,-6.094 7.296,0 0,6.094 2.51,0 L 0,0 Z"></path></g><path id="path76" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 611.079,72.619 -2.488,0 0,14.972 2.488,0 0,-14.972 z m -9.72,2.067 c 1.771,0 2.93,0.865 2.93,2.573 0,1.708 -1.159,2.572 -2.93,2.572 l -3.585,0 0,-5.145 3.585,0 z m -6.074,12.906 2.489,0 0,-5.694 3.985,0 c 2.974,0 5.019,-1.75 5.019,-4.639 0,-2.911 -2.045,-4.64 -5.019,-4.64 l -6.474,0 0,14.973 z"></path><g transform="translate(619.0374,91.7248)" id="g78"><path id="path80" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 1.897,0 c 0,-0.97 0.57,-1.519 1.688,-1.519 1.097,0 1.686,0.549 1.686,1.519 L 7.148,0 C 7.148,-2.066 5.651,-2.952 3.585,-2.952 1.497,-2.952 0,-2.066 0,0 m 9.742,-4.133 0,-14.972 -2.425,0 0,5.883 c 0,2.214 0.042,4.323 0.148,6.221 -0.949,-1.708 -2.152,-3.669 -3.374,-5.652 l -4.007,-6.452 -2.678,0 0,14.972 2.425,0 0,-6.074 c 0,-2.235 -0.021,-4.175 -0.127,-5.967 0.949,1.708 2.004,3.5 3.164,5.335 l 4.153,6.706 2.721,0 z"></path></g><g transform="translate(433.4876,62.2781)" id="g82"><path id="path84" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-14.972 -2.425,0 0,5.884 c 0,2.213 0.042,4.322 0.148,6.22 -0.95,-1.708 -2.152,-3.669 -3.374,-5.652 l -4.007,-6.452 -2.678,0 0,14.972 2.425,0 0,-6.073 c 0,-2.236 -0.022,-4.176 -0.127,-5.968 0.949,1.708 2.004,3.5 3.163,5.335 L -2.721,0 0,0 Z"></path></g><g transform="translate(450.8694,60.4436)" id="g86"><path id="path88" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -1.455,-1.729 C -3.079,-0.337 -4.196,0 -5.482,0 c -2.974,0 -4.809,-2.277 -4.809,-5.63 0,-3.395 1.877,-5.673 4.724,-5.673 1.687,0 2.762,0.675 4.323,2.045 l 1.497,-1.686 c -1.898,-1.793 -3.522,-2.532 -5.777,-2.532 -4.556,0 -7.318,3.354 -7.318,7.846 0,4.449 2.678,7.802 7.38,7.802 2.13,0 3.67,-0.633 5.462,-2.172"></path></g><g transform="translate(467.1966,60.4436)" id="g90"><path id="path92" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -1.455,-1.729 C -3.079,-0.337 -4.196,0 -5.482,0 c -2.974,0 -4.809,-2.277 -4.809,-5.63 0,-3.395 1.877,-5.673 4.724,-5.673 1.687,0 2.762,0.675 4.323,2.045 l 1.497,-1.686 c -1.898,-1.793 -3.522,-2.532 -5.777,-2.532 -4.556,0 -7.318,3.354 -7.318,7.846 0,4.449 2.678,7.802 7.38,7.802 2.13,0 3.67,-0.633 5.462,-2.172"></path></g><g transform="translate(470.3655,47.3479)" id="g94"><path id="path96" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 0.273,2.109 C 0.548,2.046 0.97,2.004 1.307,2.004 c 1.645,0 1.709,1.602 1.729,4.829 l 0.042,8.097 10.481,0 0,-14.972 -2.489,0 0,12.863 -5.651,0 -0.042,-6.41 C 5.355,2.257 4.829,-0.211 1.603,-0.211 1.012,-0.211 0.442,-0.126 0,0"></path></g><g transform="translate(499.5559,60.1692)" id="g98"><path id="path100" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -7.781,0 0,-4.091 7.254,0 0,-2.088 -7.254,0 0,-4.576 7.992,0 0,-2.108 -10.481,0 0,14.972 L 0,2.109 0,0 Z"></path></g><g transform="translate(507.1936,49.4143)" id="g102"><path id="path104" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 7.022,0 0,10.755 -5.567,0 L 1.413,7.107 C 1.35,2.657 0.612,0.929 0,0 m 9.511,12.864 0,-12.864 1.835,0 0,-5.229 -2.447,0 0,3.121 -10.354,0 0,-3.121 -2.446,0 0,5.229 1.307,0 c 0.739,1.055 1.646,2.784 1.688,7.191 l 0.042,5.673 10.375,0 z"></path></g><g transform="translate(524.681,54.7922)" id="g106"><path id="path108" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c 0,-3.374 1.877,-5.631 4.724,-5.631 2.847,0 4.703,2.257 4.703,5.631 0,3.353 -1.856,5.63 -4.703,5.63 C 1.877,5.63 0,3.353 0,0 m 11.979,0 c 0,-4.471 -2.743,-7.824 -7.255,-7.824 -4.513,0 -7.275,3.353 -7.275,7.824 0,4.47 2.762,7.823 7.275,7.823 4.512,0 7.255,-3.353 7.255,-7.823"></path></g><g transform="translate(550.5833,51.6926)" id="g110"><path id="path112" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c 0,1.476 -1.055,2.446 -2.974,2.446 l -3.922,0 0,-4.872 3.902,0 C -1.013,-2.426 0,-1.498 0,0 m -6.896,4.407 3.838,0 c 1.645,0 2.594,0.822 2.594,2.172 0,1.35 -0.928,2.046 -2.594,2.046 l -3.838,0 0,-4.218 z m 9.384,-4.576 c 0,-2.615 -1.835,-4.218 -4.618,-4.218 l -7.254,0 0,14.972 6.896,0 c 2.53,0 4.449,-1.307 4.449,-3.837 C 1.961,5.061 1.012,3.964 -0.38,3.479 1.371,2.973 2.488,1.771 2.488,-0.169"></path></g><g transform="translate(565.7923,52.7463)" id="g114"><path id="path116" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -0.633,1.835 C -1.35,3.922 -2.045,5.841 -2.572,7.634 -3.1,5.841 -3.796,3.901 -4.533,1.813 L -5.166,0 0,0 Z m 0.717,-2.066 -6.6,0 -1.16,-3.374 -2.53,0 5.398,14.972 3.269,0 5.398,-14.972 -2.594,0 -1.181,3.374 z"></path></g><g transform="translate(584.8607,60.1482)" id="g118"><path id="path120" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -4.555,0 0,-12.842 -2.488,0 0,12.842 -4.534,0 0,2.13 L 0,2.13 0,0 Z"></path></g><g transform="translate(599.4583,60.1692)" id="g122"><path id="path124" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -7.781,0 0,-4.091 7.254,0 0,-2.088 -7.254,0 0,-4.576 7.992,0 0,-2.108 -10.481,0 0,14.972 L 0,2.109 0,0 Z"></path></g><g transform="translate(603.2376,47.3479)" id="g126"><path id="path128" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 0.273,2.109 C 0.548,2.046 0.97,2.004 1.307,2.004 c 1.645,0 1.709,1.602 1.729,4.829 l 0.042,8.097 10.481,0 0,-14.972 -2.489,0 0,12.863 -5.651,0 -0.042,-6.41 C 5.355,2.257 4.829,-0.211 1.603,-0.211 1.012,-0.211 0.442,-0.126 0,0"></path></g><g transform="translate(628.2327,49.3723)" id="g130"><path id="path132" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 C 1.771,0 2.931,0.865 2.931,2.573 2.931,4.281 1.771,5.146 0,5.146 l -3.585,0 L -3.585,0 0,0 Z m -6.073,12.906 2.488,0 0,-5.694 3.985,0 c 2.974,0 5.019,-1.75 5.019,-4.639 0,-2.91 -2.045,-4.639 -5.019,-4.639 l -6.473,0 0,14.972 z"></path></g><g transform="translate(650.0208,60.4436)" id="g134"><path id="path136" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -1.455,-1.729 C -3.079,-0.337 -4.196,0 -5.482,0 c -2.974,0 -4.809,-2.277 -4.809,-5.63 0,-3.395 1.877,-5.673 4.724,-5.673 1.687,0 2.762,0.675 4.323,2.045 l 1.497,-1.686 c -1.898,-1.793 -3.522,-2.532 -5.777,-2.532 -4.556,0 -7.318,3.354 -7.318,7.846 0,4.449 2.678,7.802 7.38,7.802 2.13,0 3.67,-0.633 5.462,-2.172"></path></g><g transform="translate(659.304,54.0749)" id="g138"><path id="path140" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -2.488,0 0,-6.769 -2.489,0 0,14.972 2.489,0 0,-6.094 2.509,0 4.555,6.094 2.825,0 -5.356,-7.064 5.609,-7.908 -2.867,0 L 0,0 Z"></path></g><g transform="translate(683.2435,62.2781)" id="g142"><path id="path144" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-14.972 -2.425,0 0,5.884 c 0,2.213 0.042,4.322 0.148,6.22 -0.95,-1.708 -2.152,-3.669 -3.374,-5.652 l -4.007,-6.452 -2.678,0 0,14.972 2.425,0 0,-6.073 c 0,-2.236 -0.022,-4.176 -0.127,-5.968 0.949,1.708 2.004,3.5 3.163,5.335 L -2.721,0 0,0 Z"></path></g><g transform="translate(691.1995,66.4114)" id="g146"><path id="path148" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 1.897,0 c 0,-0.97 0.57,-1.519 1.688,-1.519 1.097,0 1.686,0.549 1.686,1.519 L 7.148,0 C 7.148,-2.066 5.651,-2.952 3.585,-2.952 1.497,-2.952 0,-2.066 0,0 m 9.742,-4.133 0,-14.972 -2.425,0 0,5.883 c 0,2.214 0.042,4.323 0.148,6.221 -0.949,-1.708 -2.152,-3.669 -3.374,-5.652 l -4.007,-6.452 -2.678,0 0,14.972 2.425,0 0,-6.074 c 0,-2.235 -0.021,-4.175 -0.127,-5.967 0.949,1.708 2.004,3.5 3.164,5.335 l 4.153,6.706 2.721,0 z"></path></g><g transform="translate(432.7073,36.9651)" id="g150"><path id="path152" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -5.567,-12.315 c -0.907,-2.025 -1.772,-2.953 -3.753,-2.953 -0.528,0 -1.266,0.106 -1.962,0.274 l 0.465,2.109 c 0.463,-0.105 0.969,-0.19 1.37,-0.19 0.675,0 1.349,0.211 1.835,1.349 l 0.084,0.169 L -12.969,0 -10.354,0 -6.348,-8.857 -2.467,0 0,0 Z"></path></g><g transform="translate(448.9495,21.9924)" id="g154"><path id="path156" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -2.51,0 0,6.77 -7.296,0 0,-6.77 -2.488,0 0,14.973 2.488,0 0,-6.095 7.296,0 0,6.095 2.51,0 L 0,0 Z"></path></g><g transform="translate(466.6477,36.9651)" id="g158"><path id="path160" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-14.973 -2.425,0 0,5.884 c 0,2.214 0.042,4.322 0.148,6.221 -0.95,-1.708 -2.152,-3.67 -3.374,-5.652 l -4.007,-6.453 -2.678,0 0,14.973 2.425,0 0,-6.073 c 0,-2.236 -0.022,-4.176 -0.127,-5.968 0.949,1.708 2.004,3.5 3.163,5.335 L -2.721,0 0,0 Z"></path></g><g transform="translate(481.3938,26.3782)" id="g162"><path id="path164" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c 0,1.477 -1.055,2.446 -2.974,2.446 l -3.922,0 0,-4.871 3.902,0 C -1.013,-2.425 0,-1.497 0,0 m -6.896,4.408 3.838,0 c 1.645,0 2.594,0.822 2.594,2.172 0,1.35 -0.928,2.045 -2.594,2.045 l -3.838,0 0,-4.217 z m 9.384,-4.576 c 0,-2.615 -1.835,-4.218 -4.618,-4.218 l -7.254,0 0,14.973 6.896,0 c 2.53,0 4.449,-1.308 4.449,-3.839 C 1.961,5.062 1.012,3.965 -0.38,3.479 1.371,2.974 2.488,1.771 2.488,-0.168"></path></g><g transform="translate(498.6487,34.8557)" id="g166"><path id="path168" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -7.781,0 0,-4.091 7.254,0 0,-2.088 -7.254,0 0,-4.576 7.992,0 0,-2.108 -10.481,0 0,14.972 L 0,2.109 0,0 Z"></path></g><g transform="translate(506.0559,34.8977)" id="g170"><path id="path172" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-5.082 3.964,0 c 1.729,0 2.826,0.886 2.826,2.531 C 6.79,-0.886 5.693,0 3.964,0 L 0,0 Z m 9.278,-2.551 c 0,-2.847 -1.94,-4.597 -4.913,-4.597 l -4.365,0 0,-5.757 -2.488,0 0,14.972 6.853,0 c 2.973,0 4.913,-1.771 4.913,-4.618"></path></g><g transform="translate(531.7874,35.1301)" id="g174"><path id="path176" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="M 0,0 -1.455,-1.729 C -3.079,-0.338 -4.196,0 -5.482,0 c -2.974,0 -4.809,-2.277 -4.809,-5.631 0,-3.394 1.877,-5.672 4.724,-5.672 1.687,0 2.762,0.675 4.323,2.045 l 1.497,-1.686 c -1.898,-1.793 -3.522,-2.531 -5.777,-2.531 -4.556,0 -7.318,3.353 -7.318,7.844 0,4.45 2.678,7.803 7.38,7.803 2.13,0 3.67,-0.633 5.462,-2.172"></path></g><g transform="translate(548.431,36.9651)" id="g178"><path id="path180" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 0,-14.973 -2.425,0 0,5.884 c 0,2.214 0.042,4.322 0.148,6.221 -0.95,-1.708 -2.152,-3.67 -3.374,-5.652 l -4.007,-6.453 -2.678,0 0,14.973 2.425,0 0,-6.073 c 0,-2.236 -0.022,-4.176 -0.127,-5.968 0.949,1.708 2.004,3.5 3.163,5.335 L -2.721,0 0,0 Z"></path></g><g transform="translate(564.3577,34.8352)" id="g182"><path id="path184" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -4.555,0 0,-12.843 -2.488,0 0,12.843 -4.534,0 0,2.13 L 0,2.13 0,0 Z"></path></g><g transform="translate(578.9554,34.8557)" id="g186"><path id="path188" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -7.781,0 0,-4.091 7.254,0 0,-2.088 -7.254,0 0,-4.576 7.992,0 0,-2.108 -10.481,0 0,14.972 L 0,2.109 0,0 Z"></path></g><g transform="translate(594.4378,34.8352)" id="g190"><path id="path192" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 -4.555,0 0,-12.843 -2.488,0 0,12.843 -4.534,0 0,2.13 L 0,2.13 0,0 Z"></path></g></g></g><g id="g194"><g clip-path="url(#clipPath198)" id="g196"><g id="g202"><g id="g204"></g><g id="g210"><g style="opacity:0" id="g212" clip-path="url(#clipPath206)"><g id="g214" transform="translate(54.7073,0.0022)"><path id="path216" style="fill:#ffffff;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c -30.213,0 -54.706,24.493 -54.706,54.706 0,30.213 24.493,54.706 54.706,54.706 30.213,0 54.706,-24.493 54.706,-54.706 C 54.706,24.493 30.213,0 0,0"></path></g></g></g></g><g transform="translate(104.4383,31.8879)" id="g218"><path id="path220" style="fill:#0f45c7;fill-opacity:1;fill-rule:nonzero;stroke:none" d="m 0,0 c 3.193,6.945 4.976,14.675 4.976,22.823 0,30.213 -24.491,54.705 -54.707,54.705 -30.214,0 -54.707,-24.492 -54.707,-54.705 0,-30.216 24.493,-54.711 54.707,-54.711 20.489,0 38.342,11.265 47.715,27.939 l -4.514,0 0,11.482 -8.638,-11.842 0,11.842 -8.653,-11.847 0,17.689 -2.425,0 c 0.338,1.289 0.604,2.607 0.806,3.945 l 0.002,0 5.232,0 0,-11.315 8.624,11.817 0,-11.817 L -2.923,17.87 -2.923,0 0,0 Z m -25.413,17.499 -5.148,0 c 0.29,1.731 0.445,3.508 0.445,5.324 0,17.81 -14.492,32.3 -32.303,32.3 -6.075,0 -11.994,-1.699 -17.119,-4.909 l 2.616,-4.172 c 4.338,2.717 9.359,4.153 14.503,4.153 15.096,0 27.373,-12.281 27.373,-27.372 0,-1.822 -0.181,-3.6 -0.523,-5.324 l -9.375,0 0,15.951 -8.676,-11.894 -0.004,11.848 -8.626,-11.819 0,20.461 -11.839,-18.782 0,18.765 -19.817,-31.199 c 0.567,-1.476 1.226,-2.901 1.988,-4.275 l 13.879,21.721 0,-17.756 11.847,18.793 0,-18.773 8.65,11.849 0,-11.842 8.64,11.838 0,-9.185 12.107,0 C -40.696,2.839 -50.709,-4.555 -62.419,-4.555 c -5.138,0 -10.142,1.435 -14.48,4.141 l -2.608,-4.178 c 5.117,-3.198 11.028,-4.886 17.088,-4.886 14.462,0 26.732,9.549 30.837,22.678 l 5.292,0 c -4.256,-15.964 -18.835,-27.76 -36.121,-27.76 -20.612,0 -37.381,16.773 -37.381,37.383 0,20.609 16.769,37.381 37.381,37.381 20.613,0 37.378,-16.772 37.378,-37.381 0,-1.811 -0.13,-3.586 -0.38,-5.324"></path></g></g></g></g></svg>
        </a>
        <ul class="menu-list">
            <li><a class="menu-link" href="#materials">Материалы</a></li>
            <li><a class="menu-link" href="#calendar">Календарь</a></li>
            <li><a href="http://t.me/mietcbot/webapp" class="menu-link">Расписание</a></li>
        </ul>
    </div>
</header>

<section class="hero">
    <h1>Добро пожаловать, студент</h1>
    <p>Сайт МИЭТ — для учебы и отслеживания событий</p>
</section>

<div class="container" id="materials">
    <div class="card">
        <h3>Учебные материалы</h3>
        <p>
            <a href="https://djvu.online/file/OujgSjm3uoYOf" target="_blank" title="Лекции и задачи по математике">📘 Математика</a>
            <a href="https://djvu.online/file/2LiPqncWFJAD7" target="_blank" title="Лекции и задачи по физике">📗 Физика</a>
            <a href="https://djvu.online/file/6zM0ORKw5Hw6h" target="_blank" title="Лекции и задачи по химии">📙 Химия</a>
        </p>
    </div>

    <div class="info">
        <h3>Удобный интерфейс</h3>
        <p>Простой и понятный дизайн — разберётся каждый</p>
    </div>
</div>

<!-- БЛОК ПРАЗДНИКОВ -->
<div class="card" id="holidays-card">
    <h3><i class="fas fa-gift"></i> Праздники</h3>
    <div id="holidays-container"><div class="holidays-list">
            <div class="holiday-item world">
                <div class="holiday-icon">👶</div>
                <div class="holiday-content">
                    <div class="holiday-name">👶 День защиты детей</div>
                    <div class="holiday-description">Праздник детства</div>
                </div>
                <div class="holiday-date">
                    <i class="fas fa-calendar-check"></i> Сегодня!
                </div>
            </div>
        </div></div>
</div>

<!-- БЛОК СЛУЧАЙНЫХ ФАКТОВ -->
<div class="card" id="facts-card">
    <h3><i class="fas fa-brain"></i> Знаете ли вы?</h3>
    <div id="fact-container">
        <div class="fact-content">
            <i class="fas fa-quote-left" style="color: #3b82f6; opacity: 0.5; margin-right: 8px;"></i>
            <span id="fact-text" style="opacity: 1; transform: translateY(0px); transition: 0.3s;">🎯 Ставь цели: стать отличником или просто счастливым — выбирай сам!</span>
        </div>
        <button class="fact-button" onclick="showRandomFact()">
            <i class="fas fa-sync-alt"></i> Другой факт
        </button>
    </div>
</div>

<script>
// ========== ПРАЗДНИКИ ==========
const holidaysDB = {
    fixed: [
        { month: 0, day: 1, name: "🎄 Новый год", type: "federal", desc: "Главный праздник года", icon: "🎄" },
        { month: 0, day: 7, name: "☦️ Рождество Христово", type: "federal", desc: "Православный праздник", icon: "☦️" },
        { month: 0, day: 13, name: "📅 Старый Новый год", type: "other", desc: "Традиционный праздник", icon: "📅" },
        { month: 0, day: 25, name: "🎓 Татьянин день", type: "other", desc: "День российского студенчества", icon: "🎓" },
        { month: 1, day: 14, name: "❤️ День всех влюблённых", type: "world", desc: "Праздник любви и романтики", icon: "❤️" },
        { month: 1, day: 23, name: "🛡️ День защитника Отечества", type: "federal", desc: "Поздравляем мужчин", icon: "🛡️" },
        { month: 2, day: 8, name: "🌷 Международный женский день", type: "federal", desc: "Поздравляем женщин", icon: "🌷" },
        { month: 3, day: 1, name: "😂 День смеха", type: "world", desc: "Шутим и веселимся", icon: "😂" },
        { month: 3, day: 12, name: "🚀 День космонавтики", type: "federal", desc: "Первый полёт человека в космос", icon: "🚀" },
        { month: 4, day: 1, name: "🌺 Праздник Весны и Труда", type: "federal", desc: "День труда", icon: "🌺" },
        { month: 4, day: 9, name: "🎖️ День Победы", type: "federal", desc: "Память о великой победе", icon: "🎖️" },
        { month: 5, day: 1, name: "👶 День защиты детей", type: "world", desc: "Праздник детства", icon: "👶" },
        { month: 5, day: 12, name: "🇷🇺 День России", type: "federal", desc: "Главный государственный праздник", icon: "🇷🇺" },
        { month: 6, day: 8, name: "💑 День семьи, любви и верности", type: "federal", desc: "Праздник семейных ценностей", icon: "💑" },
        { month: 7, day: 22, name: "🏳️ День Государственного флага РФ", type: "federal", desc: "Символ нашей страны", icon: "🏳️" },
        { month: 8, day: 1, name: "📚 День знаний", type: "federal", desc: "Начало учебного года", icon: "📚" },
        { month: 9, day: 5, name: "👩‍🏫 День учителя", type: "world", desc: "Профессиональный праздник педагогов", icon: "👩‍🏫" },
        { month: 10, day: 4, name: "🇷🇺 День народного единства", type: "federal", desc: "Единство и согласие", icon: "🇷🇺" },
        { month: 11, day: 12, name: "⚖️ День Конституции РФ", type: "federal", desc: "Главный закон страны", icon: "⚖️" },
        { month: 11, day: 31, name: "🎆 Новогодняя ночь", type: "other", desc: "Встречаем Новый год!", icon: "🎆" }
    ]
};

function getTodayHolidays() {
    const today = new Date();
    const currentMonth = today.getMonth();
    const currentDay = today.getDate();
    const todayHolidays = [];
    
    for (const holiday of holidaysDB.fixed) {
        if (holiday.month === currentMonth && holiday.day === currentDay) {
            todayHolidays.push(holiday);
        }
    }
    
    const upcomingHolidays = [];
    for (const holiday of holidaysDB.fixed) {
        let holidayDate = new Date(today.getFullYear(), holiday.month, holiday.day);
        if (holidayDate < today) {
            holidayDate = new Date(today.getFullYear() + 1, holiday.month, holiday.day);
        }
        const daysDiff = Math.ceil((holidayDate - today) / (1000 * 60 * 60 * 24));
        if (daysDiff > 0 && daysDiff <= 3) {
            upcomingHolidays.push({ ...holiday, daysLeft: daysDiff });
        }
    }
    
    return { today: todayHolidays, upcoming: upcomingHolidays };
}

function getDayWord(days) {
    if (days === 1) return 'день';
    if (days >= 2 && days <= 4) return 'дня';
    return 'дней';
}

function displayHolidays() {
    const container = document.getElementById('holidays-container');
    if (!container) return;
    
    const { today, upcoming } = getTodayHolidays();
    
    if (today.length === 0 && upcoming.length === 0) {
        container.innerHTML = `
            <div class="no-holiday">
                <div class="no-holiday-icon">
                    <i class="fas fa-calendar-day"></i>
                </div>
                <div class="no-holiday-text">
                    📅 Сегодня особых праздников нет<br>
                    <span>🌙</span> Но каждый день — повод для улыбки! <span>✨</span>
                </div>
                <div class="holiday-tip">
                    <i class="fas fa-lightbulb"></i> Загляните завтра — возможно, будет праздник!
                </div>
            </div>
        `;
        return;
    }
    
    let html = '<div class="holidays-list">';
    
    for (const holiday of today) {
        html += `
            <div class="holiday-item ${holiday.type}">
                <div class="holiday-icon">${holiday.icon}</div>
                <div class="holiday-content">
                    <div class="holiday-name">${holiday.name}</div>
                    <div class="holiday-description">${holiday.desc}</div>
                </div>
                <div class="holiday-date">
                    <i class="fas fa-calendar-check"></i> Сегодня!
                </div>
            </div>
        `;
    }
    
    for (const holiday of upcoming) {
        const dayWord = getDayWord(holiday.daysLeft);
        html += `
            <div class="holiday-item ${holiday.type}" style="opacity: 0.85;">
                <div class="holiday-icon">${holiday.icon} ⏰</div>
                <div class="holiday-content">
                    <div class="holiday-name">${holiday.name}</div>
                    <div class="holiday-description">${holiday.desc}</div>
                </div>
                <div class="holiday-date">
                    <i class="fas fa-hourglass-half"></i> Через ${holiday.daysLeft} ${dayWord}
                </div>
            </div>
        `;
    }
    
    html += '</div>';
    container.innerHTML = html;
}

// ========== ФАКТЫ ==========
const factsDB = [
    { type: "history", text: "МИЭТ был основан 26 ноября 1965 года как Московский институт электронной техники" },
    { type: "history", text: "Первый выпуск МИЭТа состоялся в 1971 году — всего 186 инженеров" },
    { type: "campus", text: "В МИЭТе учатся студенты из более чем 40 стран мира" },
    { type: "campus", text: "Библиотека МИЭТа насчитывает более 1 миллиона книг и учебников" },
    { type: "science", text: "МИЭТ входит в топ-10 технических вузов России по версии RAEX" },
    { type: "science", text: "Студенты МИЭТа разработали первый российский микроконтроллер для космоса" },
    { type: "alumni", text: "Среди выпускников МИЭТа — основатели YADRO и других IT-гигантов" },
    { type: "alumni", text: "Выпускники МИЭТа работают в Google, Intel, Samsung и других мировых корпорациях" },
    { type: "fun", text: "В МИЭТе есть своя киберспортивная команда, которая побеждает на всероссийских турнирах" },
    { type: "fun", text: "Студенческий театр МИЭТа существует уже более 30 лет" },
    { type: "motivation", text: "🎒 Не забудь рюкзак — в нём твои знания и второй завтрак!" },
    { type: "motivation", text: "📚 Если плохо будешь учиться — лучше исправляйся, мир ждёт твоих талантов!" },
    { type: "motivation", text: "☕ Кофе — это хорошо, но сон — лучше. Высыпайся перед экзаменом!" },
    { type: "motivation", text: "💡 Одна прочитанная лекция лучше двух пропущенных" },
    { type: "motivation", text: "⏰ Не откладывай на завтра то, что можно сдать послезавтра... но лучше сдать сегодня!" },
    { type: "motivation", text: "🧠 Гугл — лучший друг студента, но свои знания — лучший помощник" },
    { type: "motivation", text: "🎯 Ставь цели: стать отличником или просто счастливым — выбирай сам!" },
    { type: "motivation", text: "💪 Помни: даже таблица Менделеева когда-то приснилась во сне!" },
    { type: "motivation", text: "🕐 Время — это деньги. А на сессии — это деньги вдвойне!" },
    { type: "motivation", text: "🎓 Диплом — это не финиш, а старт твоей крутой карьеры!" },
    { type: "motivation", text: "🏆 Лучший студент не тот, у кого нет проблем, а тот, кто их решает" },
    { type: "motivation", text: "✨ Учёба сложна, но результат стоит усилий. Ты сможешь!" },
    { type: "motivation", text: "📱 Телефон не убежит, а лекцию можно прослушать" },
    { type: "motivation", text: "🍎 Яблоко в день — и шпаргалки не понадобятся!" },
    { type: "motivation", text: "🎉 Самый лучший студент — это ты! Просто пока не знаешь об этом" }
];

let usedIndices = [];

function getRandomFact() {
    if (usedIndices.length >= factsDB.length) {
        usedIndices = [];
    }
    
    let availableIndices = [];
    for (let i = 0; i < factsDB.length; i++) {
        if (!usedIndices.includes(i)) {
            availableIndices.push(i);
        }
    }
    
    const randomIndex = availableIndices[Math.floor(Math.random() * availableIndices.length)];
    usedIndices.push(randomIndex);
    return factsDB[randomIndex];
}

function showRandomFact() {
    const factElement = document.getElementById('fact-text');
    if (!factElement) return;
    
    const fact = getRandomFact();
    
    factElement.style.opacity = '0';
    factElement.style.transform = 'translateY(10px)';
    
    setTimeout(() => {
        factElement.innerHTML = fact.text;
        factElement.style.opacity = '1';
        factElement.style.transform = 'translateY(0)';
        factElement.style.transition = 'all 0.3s ease';
    }, 150);
}

// Запуск при загрузке страницы
document.addEventListener('DOMContentLoaded', function() {
    displayHolidays();
    showRandomFact();
});

// Обновление праздников каждый час
setInterval(displayHolidays, 60 * 60 * 1000);
// Обновление фактов каждые 30 секунд
setInterval(showRandomFact, 30000);
</script>


</body></html>
