# Postman
<!DOCTYPE html>
<html lang="en" style="overflow-y: scroll;">
<head>
  <meta charset="UTF-8">
  <title>Newman Summary Report</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css">
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.1.2/styles/default.min.css">
  <link rel="stylesheet" href="https://cdn.datatables.net/v/bs4/dt-1.10.18/datatables.min.css"/>

<style>
code.renderMarkdown table, code.renderMarkdown th, code.renderMarkdown td {
    border: 1px solid black;
    width: max-content;
    padding: .75rem;
}

.theme-dark {
    --background-color: #222;
    --bg-card-deck: #444444;
    --text-color: #ccd2d8;
    --tab-border: solid 1px #444;
    --success: #3c9372;
    --failure: #c24a3f;
    --warning: #d28c23;
    --info: #4083b6;
    --badge-outline: #3c9372;
    --badge-bg: #cdd3db;
    --badge-text: #ccd2d9;
    --failure-row: #c24a3f;
    --warning-row: #d28c23;
    --card-bg: #444;
    --card-footer: #4f5758;
    --form-input: #ececb5;
    --hov-text: #d2dae5;
    --h4-text: #ccd1d9;
}

.theme-light {
    --tab-border: solid 1px #fff;
    --text-color: #000000;
    --success: #42a745;
    --failure: #dc3544;
    --warning: #f4c10b;
    --info: #49a1b8;
    --badge-outline: #040411;
    --badge-bg: #f8f9fa;
    --badge-text: #fff;
    --failure-row: #f5c6cb;
    --warning-row: #ffeeba;
    --card-bg: #f7f7f7;
    --hov-text: #fff;
    --h4-text: #ffffff;
}

body {
  padding-top:30px;
  background-color: var(--background-color)!important;
  color: var(--text-color);
}

#execution-data {
  padding: 10px;
  border: var(--tab-border);
  border-top: none;
}

.nav-tabs {
  padding-top: 10px;
  height: 105px;
  overflow-y: auto;
}

body.theme-dark .card-header {
    background-color: #444;
}

body.theme-light .card-header {
    background-color: #f7f7f7;
}

.card-footer {
    padding: .75rem 1.25rem;
    background-color: var(--card-footer);
}

.card-deck {
    background-color: var(--bg-card-deck)!important;
}
.form-control {
    background: var(--form-input);
}

.custom-tab {
  padding: 10px 15px;
  margin-right: 0px;
  height: 47px;
  width: 69px;
  text-align: center;
  border: var(--tab-border);
  border-bottom: none;
  cursor:pointer;
}

body.theme-dark .text-white {
    color: #ccd2d9!important;
}
h4 {
    color: var(--h4-text);
}

body.theme-dark h1 {
    color: #ccd2da;
}

body.theme-dark .bg-light>td {
    background: #4f5858!important;
}

body.theme-dark .hljs {
    background: #0a0a0ab0!important;
    color: #8d8787!important;
}

.bg-info {
    background-color: var(--info)!important;
}
.bg-success {
    background-color: var(--success)!important;
}

.alert-success {
    background-color: var(--success)!important;
}

.alert-warning {
    background-color: var(--warning)!important;
}

.alert-info {
    background-color: var(--info)!important;
}

.bg-warning {
    background-color: var(--warning)!important;
}

.badge-warning {
    color: var(--badge-text)!important;
    background-color: var(--warning)!important;
}

.table-warning>td {
    background-color: var(--warning-row);
}

.alert-danger {
    background-color: var(--failure)!important;
}

body.theme-dark .alert-dark {
    background-color: #636467!important;
}

body.theme-dark .text-dark {
    color: #d1dae4!important;
}

body.theme-dark .badge-light {
    color: #212529;
    background-color: #cdd3db;
}

body.theme-light .badge-light {
    color: #212529;
    background-color: #f8f9fa;
}
body.theme-light .bg-danger {
    background-color: var(--failure)!important;
}

body.theme-dark .bg-danger {
    background-color: var(--failure)!important;
}

.table-danger>td {
    background-color: var(--failure-row);
}

body.theme-dark .table .thead-light th {
    background-color: #4f5858!important;
    border-color: #dee2e6!important;
    color: #ccd2d8!important;
}

.itPassed {
  background: var(--success);
  color: white;
}
.itFailed {
  background: var(--failure);
  color: white;
}

.resultsInfoPass {
  color: var(--success);
  padding-top: 4px;
}

.resultsInfoFail {
  color: var(--failure);
  padding-top: 4px;
}

.badge-outline-success {
  color: var(--success);
  border: 1px solid var(--success);
  background-color: transparent;
}

.badge-outline {
  color: var(--badge-outline);
  border: 1px solid var(--badge-outline);
  background-color: transparent;
}

.btn-outline-success {
    color: var(--success)!important;
    border-color: var(--success)!important;
}

.backToTop:hover {
  background-color: var(--success);
  border-color: var(--success);
  color: var(--hov-text)!important;
}

.btn-outline-success:hover {
  background-color: var(--success);
  border-color: var(--success);
  color: var(--hov-text)!important;
}

.btn-outline-secondary {
  background-color: var(--success)!important;
  color: var(--hov-text)!important;
}

body.theme-dark .env-heading {
    color: #ccd2d9!important;
}

body, html {
  height:100%;
}

.card {
  overflow:hidden;
}

body.theme-dark .card-body {
    background-color: #444;
}

body.theme-light .card-body {
    background-color: #f7f7f7;
}

body.theme-dark .card-body .bg-danger {
    background-color: var(--failure)!important;
}

body.theme-light .card-body .bg-danger {
    background-color: var(--failure)!important;
}

.card-body .rotate {
  z-index: 8;
  float: right;
  height: 100%;
}

.card-body .rotate i {
  color: #14141426;
  position: absolute;
  left: 0;
  left: auto;
  right: -10px;
  bottom: 0;
  display: block;
  -webkit-transform: rotate(-44deg);
  -moz-transform: rotate(-44deg);
  -o-transform: rotate(-44deg);
  -ms-transform: rotate(-44deg);
  transform: rotate(-44deg);
}

.dyn-height {
  max-height:350px;
  overflow-y:auto;
}

.nav-pills .nav-link.active {
  background-color: transparent!important;
}

.backToTop {
  display: none;
  position: fixed;
  bottom: 10px;
  right: 20px;
  z-index: 99;
  font-size: 15px;
  outline: none;
  cursor: pointer;
  padding: 15px;
  border-radius: 4px;
}

.card-header .fa {
  transition: .3s transform ease-in-out;
}
.card-header .collapsed .fa {
  transform: rotate(90deg);
}

.single-line-tabs {
  padding-top: 10px;
  height: 60px;
}

::-webkit-scrollbar {
  width: 5px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #888;
}

::-webkit-scrollbar-thumb:hover {
  background: #555;
}

/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 44px;
  height: 20px;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider */
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 20px;
  width: 20px;
  left: 0px;
  bottom: 4px;
  top: 0;
  bottom: 0;
  margin: auto 0;
  -webkit-transition: 0.4s;
  transition: 0.4s;
  box-shadow: 0 0px 15px #2020203d;
  background: white;
  background-repeat: no-repeat;
  background-position: center;
}

input:checked + .slider {
  background-color: #4083b6;
}

input:focus + .slider {
  box-shadow: 0 0 1px #4083b6;
}

input:checked + .slider:before {
  -webkit-transform: translateX(24px);
  -ms-transform: translateX(24px);
  transform: translateX(24px);
  background: white;
  background-repeat: no-repeat;
  background-position: center;
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

table.dataTable td, table.dataTable tr {
    vertical-align: middle;
}

body.theme-dark code {
    color: #ccd2d8!important;
}

body.theme-light code {
    color: #000000!important;
}

.text-wrap {
    word-wrap: break-word; 
    min-width: 600px; 
    max-width: 600px; 
    white-space: normal;
}

</style>
</head>
<body class="theme-dark">
<script>
    function setTheme(themeName) {
        localStorage.setItem('theme', themeName);
        document.body.className = themeName;
    }

    function toggleTheme() {
        if (localStorage.getItem('theme') === 'theme-light') {
            setTheme('theme-dark');
        } else {
            setTheme('theme-light');
        }
    }
</script>
  <div class="container">
        <div class="container">
            <label>Light</label>
            <label id="switch" class="switch">
                <input type="checkbox" onchange="toggleTheme()" id="slider">
                <span class="slider round"></span>
            </label>
            <label>Dark</label>
        </div>
        <div class="card">
        <div class="card-header">
            <ul class="nav nav-pills mb-3 nav-justified" id="pills-tab" role="tablist">
            <li class="nav-item bg-info active" data-toggle="tooltip" title="Click to view the Summary">
                <a class="nav-link text-white" id="pills-summary-tab" data-toggle="pill" href="#pills-summary" role="tab" aria-controls="pills-summary" aria-selected="true">Summary</a>
            </li>
            <li class="nav-item bg-success" data-toggle="tooltip" title="Click to view the Requests">
                <a class="nav-link text-white" id="pills-requests-tab" data-toggle="pill" href="#pills-requests" role="tab" aria-controls="pills-requests" aria-selected="false">Total Requests <span class="badge badge-light">6</span></a>
            </li>
            <li class="nav-item bg-danger" data-toggle="tooltip" title="Click to view the Failed Tests">
                <a class="nav-link text-white" id="pills-failed-tab" data-toggle="pill" href="#pills-failed" role="tab" aria-controls="pills-failed" aria-selected="false">Failed Tests <span class="badge badge-light">0</span></a>
            </li>
            <li class="nav-item bg-warning" data-toggle="tooltip" title="Click to view the Skipped Tests">
                <a class="nav-link text-white" id="pills-skipped-tab" data-toggle="pill" href="#pills-skipped" role="tab" aria-controls="pills-skipped" aria-selected="false">Skipped Tests <span class="badge badge-light">0</span></a>
            </li>
            </ul>
        <div class="tab-content" id="pills-tabContent">
            <div class="tab-pane fade show active" id="pills-summary" role="tabcard" aria-labelledby="pills-summary-tab">
<div class="row">
  <div class="col-md-9 col-lg-12 main">
   <h1 class="display-2 text-center">Newman Run Dashboard</h1>
   <h5 class="text-center">Sunday, 26 March 2023 03:40:36</h5>
   <div class="row">
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-success">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-retweet fa-5x"></i>
       </div>
       <h6 class="text-uppercase">Total Iterations</h6>
       <h1 class="display-1">1</h1>
      </div>
     </div>
    </div>
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-danger">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-list fa-4x"></i>
       </div>
       <h6 class="text-uppercase">Total Assertions</h6>
       <h1 class="display-1">52</h1>
      </div>
     </div>
    </div>
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-info">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-plus-circle fa-5x"></i>
       </div>
       <h6 class="text-uppercase">Total Failed Tests</h6>
       <h1 class="display-1">0</h1>
      </div>
     </div>
    </div>
    <div class="col-lg-3 col-md-6">
     <div class="card text-white card-warning">
      <div class="card-body bg-success">
       <div class="rotate">
        <i class="fa fa-share fa-5x"></i>
       </div>
       <h6 class="text-uppercase">Total Skipped Tests</h6>
       <h1 class="display-1">0</h1>
      </div>
     </div>
    </div>
   </div>
   <hr>
    <div class="row">
    <div class="col">
        <div class="row">
        <div class="col-sm-12 mb-3">
            <div class="card border-info">
                <div class="card-body">
                <h5 class="card-title text-uppercase text-white text-center bg-info">File Information</h5>
                <span><i class="fas fa-file-code"></i></span><strong> Collection:</strong> VK Server courses_HW2<br>
                
                <span><i class="fas fa-file-code"></i></span><strong> Environment:</strong> VK_HW2<br>
                </div>
            </div>
        </div>
        </div>
        <div class="row">
        <div class="col-sm-12 mb-3">
            <div class="card border-info">
                <div class="card-body">
                <h5 class="card-title text-uppercase text-white text-center bg-info">Timings and Data</h5>
                <span><i class="fas fa-stopwatch"></i></span><strong> Total run duration:</strong> 715ms<br>
                <span><i class="fas fa-database"></i></span><strong> Total data received:</strong> 1.33KB<br>
                <span><i class="fas fa-stopwatch"></i></span><strong> Average response time:</strong> 101ms<br>
                </div>
            </div>
        </div>
        </div>
        <div class="row">
        <div class="col-sm-12 mb-3">
            <div class="table-responsive">
            <table class="table table-striped table-bordered">
                <thead class="thead-inverse">
                    <tr class="text-center">
                        <th class="text-uppercase">Summary Item</th>
                        <th class="text-uppercase">Total</th>
                        <th class="text-uppercase">Failed</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Requests</td>
                        <td class="text-center">6</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr>
                        <td>Prerequest Scripts</td>
                        <td class="text-center">0</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr>
                        <td>Test Scripts</td>
                        <td class="text-center">6</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr class="">
                        <td>Assertions</td>
                        <td class="text-center">52</td>
                        <td class="text-center">0</td>
                    </tr>
                    <tr class="">
                        <td>Skipped Tests</td>
                        <td class="text-center">0</td>
                        <td class="text-center">-</td>
                    </tr>
                </tbody>
            </table>
            </div>
        </div>
        </div>
    <hr>
   </div>
   </div>
  </div>
 </div>
        </div>
            <div class="tab-pane fade" id="pills-failed" role="tabcard" aria-labelledby="pills-failed-tab">
                <button id="topOfFailuresScreen" class="btn btn-outline-success btn-sm backToTop" onclick="topFunction()">Go To Top</button>

                <div class="alert alert-success text-uppercase text-center">
                     <br><br><h1 class="text-center">There are no failed tests <span><i class="far fa-thumbs-up"></i></span></h1><br><br>
                </div>
            </div>

            <div class="tab-pane fade" id="pills-skipped" role="tabcard" aria-labelledby="pills-skipped-tab">
                <button id="topOfSkippedScreen" class="btn btn-outline-success btn-sm backToTop" onclick="topFunction()">Go To Top</button>

                <div class="alert alert-success text-uppercase text-center">
                    <br><br><h1 class="text-center">There are no skipped tests <span><i class="far fa-thumbs-up"></i></span></h1><br><br>
                </div>
            </div>
            <div class="tab-pane fade" id="pills-requests" role="tabcard" aria-labelledby="pills-requests-tab">

            <button id="topOfRequestsScreen" class="btn btn-outline-success btn-sm backToTop" onclick="topFunction()">Go To Top</button>

            <div class="btn-group float-right" role="group" aria-label="Button Group">
                <button id="openAll" class="btn btn-outline-success btn-sm float-right" style="text-align: center; width: 140px;">Expand Folders</button>
                <button id="openAllRequests" class="btn btn-outline-success btn-sm float-right" style="text-align: center; width: 140px;">Expand Requests</button>
            </div>

    <div class="text-uppercase" id="execution-menu">
        <h5>1 Iteration available to view</h5>
        
        <nav class="table-responsive">
        <ul class="nav single-line-tabs" id="iterationList">
        </ul>
        </nav>
    </div>
    <h6 class="text-uppercase text-muted" id="iterationSelected" style="padding-top: 10px;"></h6>
	<div class="tab-content" id="execution-data">
            <div id="folder-cb06e661-f9be-4e6b-8948-7aa470992e1b" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b" aria-expanded="false" aria-controls="collapse" id="requests-cb06e661-f9be-4e6b-8948-7aa470992e1b" class="collapsed text-white z-block">
                    Iteration: 1 - /first_HW2 <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b" class="collapse" aria-labelledby="requests-cb06e661-f9be-4e6b-8948-7aa470992e1b">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="http://162.55.220.72:5005/first" target="_blank">http://162.55.220.72:5005/first</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 106ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 41B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.29.0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">ac55644f-cf81-4bc9-9254-dc796263151f</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">162.55.220.72:5005</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">text/html; charset&#x3D;utf-8</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">41</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Werkzeug/2.0.1 Python/3.8.10</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Sun, 26 Mar 2023 01:40:35 GMT</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-f573c3f0-75ce-48c8-8d5d-4246b2d92a26" class="prettyPrint">This is the first responce from server!ss</code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-f573c3f0-75ce-48c8-8d5d-4246b2d92a26">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Status code is 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body matches string</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">2</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-5f24eaa1-00d5-4cca-8170-36b6d700d397" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397" aria-expanded="false" aria-controls="collapse" id="requests-5f24eaa1-00d5-4cca-8170-36b6d700d397" class="collapsed text-white z-block">
                    Iteration: 1 - /object_info_3_HW2 <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397" class="collapse" aria-labelledby="requests-5f24eaa1-00d5-4cca-8170-36b6d700d397">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="http://162.55.220.72:5005/object_info_3?name&#x3D;Misha&amp;age&#x3D;34&amp;salary&#x3D;800" target="_blank">http://162.55.220.72:5005/object_info_3?name&#x3D;Misha&amp;age&#x3D;34&amp;salary&#x3D;800</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 103ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 377B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.29.0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">4d3ccb32-af0c-4098-be26-72b57deada84</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">162.55.220.72:5005</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">377</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Werkzeug/2.0.1 Python/3.8.10</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Sun, 26 Mar 2023 01:40:35 GMT</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-47f6aada-ead1-4eed-aaa1-1882edae56b4" class="prettyPrint">{
          &quot;age&quot;: &quot;34&quot;, 
          &quot;family&quot;: {
            &quot;children&quot;: [
              [
                &quot;Alex&quot;, 
                24
              ], 
              [
                &quot;Kate&quot;, 
                12
              ]
            ], 
            &quot;pets&quot;: {
              &quot;cat&quot;: {
                &quot;age&quot;: 3, 
                &quot;name&quot;: &quot;Sunny&quot;
              }, 
              &quot;dog&quot;: {
                &quot;age&quot;: 4, 
                &quot;name&quot;: &quot;Luky&quot;
              }
            }, 
            &quot;u_salary_1_5_year&quot;: 3200
          }, 
          &quot;name&quot;: &quot;Misha&quot;, 
          &quot;salary&quot;: 800
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-47f6aada-ead1-4eed-aaa1-1882edae56b4">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Req_Resp_name_check</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_age_check</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_salary_check</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - Dog_Name</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - Dog_Age</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - Dog_Name_Luky</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - Dog_Age_4</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">7</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-c4f25e75-8204-4483-9e19-ff7be8cffeac" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac" aria-expanded="false" aria-controls="collapse" id="requests-c4f25e75-8204-4483-9e19-ff7be8cffeac" class="collapsed text-white z-block">
                    Iteration: 1 - /object_info_4 HW2 <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac" class="collapse" aria-labelledby="requests-c4f25e75-8204-4483-9e19-ff7be8cffeac">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="http://162.55.220.72:5005/object_info_4?name&#x3D;Misha&amp;age&#x3D;34&amp;salary&#x3D;1200" target="_blank">http://162.55.220.72:5005/object_info_4?name&#x3D;Misha&amp;age&#x3D;34&amp;salary&#x3D;1200</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 101ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 91B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.29.0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">2ab6e7c3-67da-4eaa-a5ae-90639a656284</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">162.55.220.72:5005</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">91</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Werkzeug/2.0.1 Python/3.8.10</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Sun, 26 Mar 2023 01:40:35 GMT</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-3bef7511-67d3-4597-807f-11dddd84de9e" class="prettyPrint">{
          &quot;age&quot;: 34, 
          &quot;name&quot;: &quot;Misha&quot;, 
          &quot;salary&quot;: [
            1200, 
            &quot;2400&quot;, 
            &quot;3600&quot;
          ]
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-3bef7511-67d3-4597-807f-11dddd84de9e">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Status code is 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_resp_name</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_resp_age</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_resp_salary_1</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_resp_salary_2</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_resp_salary_3</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">6</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-ce340ea9-efe6-48ca-95e6-df0fcf5244f8" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8" aria-expanded="false" aria-controls="collapse" id="requests-ce340ea9-efe6-48ca-95e6-df0fcf5244f8" class="collapsed text-white z-block">
                    Iteration: 1 - /user_info_3_HW2 <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8" class="collapse" aria-labelledby="requests-ce340ea9-efe6-48ca-95e6-df0fcf5244f8">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="http://162.55.220.72:5005/user_info_3" target="_blank">http://162.55.220.72:5005/user_info_3</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 98ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 223B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.29.0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">9cbdb278-5846-4972-a46b-fce753e8e778</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">162.55.220.72:5005</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">377</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                            <div class="row">
                                <div class="col-sm-12 mb-3">
                                    <div class="card-deck">
                                        <div class="card border-info" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                                <div class="dyn-height">
                                                    <pre><code id="copyReqText-3" class="prettyPrint">{&quot;age&quot;:&quot;34&quot;,&quot;name&quot;:&quot;Misha&quot;,&quot;salary&quot;:&quot;1000&quot;}</code></pre>
                                                </div>
                                                <div class="card-footer">
                                                    <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-3">Copy to Clipboard</button>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">223</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Werkzeug/2.0.1 Python/3.8.10</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Sun, 26 Mar 2023 01:40:36 GMT</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-e833b6a0-b51f-4e46-ab42-b1872acbfa0d" class="prettyPrint">{
          &quot;age&quot;: &quot;34&quot;, 
          &quot;family&quot;: {
            &quot;children&quot;: [
              [
                &quot;Alex&quot;, 
                24
              ], 
              [
                &quot;Kate&quot;, 
                12
              ]
            ], 
            &quot;u_salary_1_5_year&quot;: 4000
          }, 
          &quot;name&quot;: &quot;Misha&quot;, 
          &quot;salary&quot;: 1000
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-e833b6a0-b51f-4e46-ab42-b1872acbfa0d">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Req_Resp_Name_manual</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_Age_manual</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_Salary_manual</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_Name</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_Age</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_Salary</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Req_Resp_Salary_1_5</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">7</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-37b14767-e282-4a5f-a49b-60239c17d0a3" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-37b14767-e282-4a5f-a49b-60239c17d0a3" aria-expanded="false" aria-controls="collapse" id="requests-37b14767-e282-4a5f-a49b-60239c17d0a3" class="collapsed text-white z-block">
                    Iteration: 1 - /user_info_2_HW2 <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-37b14767-e282-4a5f-a49b-60239c17d0a3" class="collapse" aria-labelledby="requests-37b14767-e282-4a5f-a49b-60239c17d0a3">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> POST</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="http://162.55.220.72:5005/user_info_2" target="_blank">http://162.55.220.72:5005/user_info_2</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 109ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 317B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.29.0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">761ea29e-d2c4-473b-bb32-2776b83d5f0b</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">162.55.220.72:5005</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Content-Length</td>
                                                        <td class="text-wrap">377</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                            <div class="row">
                                <div class="col-sm-12 mb-3">
                                    <div class="card-deck">
                                        <div class="card border-info" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-info">Request Body</h5>
                                                <div class="dyn-height">
                                                    <pre><code id="copyReqText-4" class="prettyPrint">{&quot;name&quot;:&quot;Misha&quot;,&quot;salary&quot;:&quot;1200&quot;,&quot;age&quot;:&quot;34&quot;}</code></pre>
                                                </div>
                                                <div class="card-footer">
                                                    <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyReqText-4">Copy to Clipboard</button>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">317</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Werkzeug/2.0.1 Python/3.8.10</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Sun, 26 Mar 2023 01:40:36 GMT</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-04148584-aa2a-4e5b-ba7f-ee20900f63d6" class="prettyPrint">{
          &quot;person&quot;: {
            &quot;u_age&quot;: 34, 
            &quot;u_name&quot;: [
              &quot;Misha&quot;, 
              1200, 
              34
            ], 
            &quot;u_salary_5_years&quot;: 5040.0
          }, 
          &quot;qa_salary_after_1.5_year&quot;: 3960.0, 
          &quot;qa_salary_after_12_months&quot;: 3240.0, 
          &quot;qa_salary_after_3.5_years&quot;: 4560.0, 
          &quot;qa_salary_after_6_months&quot;: 2400, 
          &quot;start_qa_salary&quot;: 1200
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-04148584-aa2a-4e5b-ba7f-ee20900f63d6">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Status code is 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - Start_qa_salary</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_6_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_12_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_1.5_year</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_3.5_years</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - person</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_start_salary</td>
                                                    <td class="text-center bg-success">2</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_6_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_12_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_1_5_years</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_u_name_salary</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_u_name_age</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_5_years</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">15</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
            <div id="folder-5abc7f8b-c989-4251-874a-e2fbbe8174b6" class="card-deck iteration-0">
            <div class="row iteration-0">
                <div class="col-sm-12 mb-3 iteration-0">
                <div class="card iteration-0">
                    <div class="card-header  bg-success iteration-0">
                        <a data-toggle="collapse" href="#" data-target="#collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6" aria-expanded="false" aria-controls="collapse" id="requests-5abc7f8b-c989-4251-874a-e2fbbe8174b6" class="collapsed text-white z-block">
                    Iteration: 1 - /object_info_2_HW2_[extra _my_mistake] <i class="float-lg-right fa fa-chevron-down" style="padding-top: 5px;"></i>
                </a>
                    </div>
                    <div id="collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6" class="collapse" aria-labelledby="requests-5abc7f8b-c989-4251-874a-e2fbbe8174b6">
                    <div class="card-body">
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Request Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request Method:</strong> <span class="badge-outline-success badge badge-success"> GET</span><br>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Request URL:</strong> <a href="http://162.55.220.72:5005/object_info_2?name&#x3D;Misha&amp;age&#x3D;34&amp;salary&#x3D;1200" target="_blank">http://162.55.220.72:5005/object_info_2?name&#x3D;Misha&amp;age&#x3D;34&amp;salary&#x3D;1200</a><br>
                                    </div>
                                </div>
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Information</h5>
                                    <span><i class="fas fa-info-circle"></i></span><strong> Response Code:</strong> <span class="float-right badge-outline badge badge-success"> 200 - OK</span><br>
                                    <span><i class="fas fa-stopwatch"></i></span><strong> Mean time per request:</strong> <span class="float-right badge-outline badge badge-success"> 93ms</span><br>
                                    <span><i class="fas fa-database"></i></span><strong> Mean size per request:</strong> <span class="float-right badge-outline badge badge-success"> 317B</span><br>
                                    <hr>
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Test Pass Percentage</h5>
                                    <div>
                                        <div class="progress" style="height: 40px;">
                                            <div class="progress-bar  bg-success" style="width: 100%" role="progressbar">
                                            <h5 style="padding-top:5px;"><strong>100 %</strong></h5>
                                            </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 mb-3">
                                <div class="card-deck">
                                <div class="card border-info" style="width: 50rem;">
                                    <div class="card-body">
                                        <h5 class="card-title text-uppercase text-white text-center bg-info">Request Headers</h5>
                                        <div class="table-responsive">
                                            <table class="table table-bordered">
                                            <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                                <tbody>
                                                    <tr>
                                                        <td class="text-nowrap">User-Agent</td>
                                                        <td class="text-wrap">PostmanRuntime/7.29.0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept</td>
                                                        <td class="text-wrap">*/*</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Cache-Control</td>
                                                        <td class="text-wrap">no-cache</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Postman-Token</td>
                                                        <td class="text-wrap">79d75135-bc14-4ec8-84e5-62b7ac87cdd0</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Host</td>
                                                        <td class="text-wrap">162.55.220.72:5005</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Accept-Encoding</td>
                                                        <td class="text-wrap">gzip, deflate, br</td>
                                                    </tr>
                                                    <tr>
                                                        <td class="text-nowrap">Connection</td>
                                                        <td class="text-wrap">keep-alive</td>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </div>
                                    </div>
                                </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Headers</h5>
                                    <div class="table-responsive">
                                        <table class="table table-bordered">
                                        <thead class="thead-light text-center"><tr><th>Header Name</th><th>Header Value</th></tr></thead>
                                            <tbody>
                                                <tr>
                                                    <td class="text-nowrap">Content-Type</td>
                                                    <td class="text-wrap">application/json</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Content-Length</td>
                                                    <td class="text-wrap">317</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Server</td>
                                                    <td class="text-wrap">Werkzeug/2.0.1 Python/3.8.10</td>
                                                </tr>
                                                <tr>
                                                    <td class="text-nowrap">Date</td>
                                                    <td class="text-wrap">Sun, 26 Mar 2023 01:40:36 GMT</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>
                            </div>
                        </div>
                        </div>
                        <div class="row">
                        <div class="col-sm-12 mb-3">
                            <div class="card-deck">
                            <div class="card border-info" style="width: 50rem;">
                                <div class="card-body">
                                    <h5 class="card-title text-uppercase text-white text-center bg-info">Response Body</h5>
                                        <div class="dyn-height">
                                                <pre><code id="copyText-f8c54a61-0e02-4efc-9d0f-41b0f90a515b" class="prettyPrint">{
          &quot;person&quot;: {
            &quot;u_age&quot;: 34, 
            &quot;u_name&quot;: [
              &quot;Misha&quot;, 
              1200, 
              34
            ], 
            &quot;u_salary_5_years&quot;: 5040.0
          }, 
          &quot;qa_salary_after_1.5_year&quot;: 3960.0, 
          &quot;qa_salary_after_12_months&quot;: 3240.0, 
          &quot;qa_salary_after_3.5_years&quot;: 4560.0, 
          &quot;qa_salary_after_6_months&quot;: 2400, 
          &quot;start_qa_salary&quot;: 1200
        }
        </code></pre>
                                        </div>
                                        <div class="card-footer">
                                            <button class="btn btn-outline-secondary btn-sm copyButton" type="button" data-clipboard-action="copy" data-clipboard-target="#copyText-f8c54a61-0e02-4efc-9d0f-41b0f90a515b">Copy to Clipboard</button>
                                        </div>
                                </div>
                            </div>
                            </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="card border-info">
                                <div class="card-body">
                                <h5 class="card-title text-uppercase text-white text-center bg-info">Test Information</h5>
                                    <div class="table-responsive text-nowrap">
                                        <table class="datatable table table-hover">
                                        <thead><tr class="text-center"><th>Name</th><th>Passed</th><th>Failed</th><th>Skipped</th></tr></thead>
                                            <tbody>
                                                <tr >
                                                    <td >Status code is 200</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - Start_qa_salary</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_6_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_12_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_1.5_year</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - qa_salary_after_3.5_years</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Body has - person</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_start_salary</td>
                                                    <td class="text-center bg-success">2</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_6_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_12_months</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_1_5_years</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_u_name_salary</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_u_name_age</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                                <tr >
                                                    <td >Resp_req_salary_5_years</td>
                                                    <td class="text-center bg-success">1</td>
                                                    <td class="text-center ">0</td>
                                                    <td class="text-center ">0</td>
                                                </tr>
                                            </tbody>
                                            <tfoot>
                                                <tr class="bg-light">
                                                    <td><strong>Total</strong></td>
                                                    <td class="text-center">15</td>
                                                    <td class="text-center">0</td>
                                                    <td class="text-center">0</td>
                                                </tr>
                                            </tfoot>
                                        </table>
                                    </div>
                                    <div class="row d-none">
                                    <div class="col-sm-12 mb-3">
                                        <div class="card-deck">
                                        <div class="card border-danger" style="width: 50rem;">
                                            <div class="card-body">
                                                <h5 class="card-title text-uppercase text-white text-center bg-danger">Test Failure</h5>
                                                <div class="table-responsive">
                                                    <table class="table table-hover">
                                                    <thead><tr class="text-nowrap"><th>Test Name</th><th>Assertion Error</th></tr></thead>
                                                        <tbody>
                                                        </tbody>
                                                    </table>
                                                </div>
                                            </div>
                                        </div>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
        </div>
    </div>
    </div>
    </div>
    </div>
    </div>


<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.2.1/js/bootstrap.bundle.min.js"></script>
<script src="https://cdn.datatables.net/v/bs4/dt-1.10.18/datatables.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.0/clipboard.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/remarkable/1.7.1/remarkable.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/10.1.2/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>

<!-- Set slider initial position depending on the localstorage state -->

<script>
(function () {
  var sliderChecked = true;
  if (localStorage.getItem('theme') === 'theme-light') {
    setTheme('theme-light');
    sliderChecked = false;
  } else {
    setTheme('theme-dark');
    sliderChecked = true;
  }
  $(document).ready( function () {
    document.getElementById('slider').checked = sliderChecked;
  });
})();
</script>

<!-- Data Table Configuration -->

<script>
$(document).ready( function () {
    $('.datatable').DataTable({
        "retrieve": true,
        "paging": false,
        "info": false,
        "fixedColumns":   {
            "heightMatch": 'none'
        }
    });
});
</script>

<!-- Tooltip Configuration -->

<script>
$(document).ready(function() {
    $('[data-toggle="tooltip"]').tooltip({
        trigger : 'hover'
    })
})
</script>

<!-- Show/Hide The Folders -->

<script>
$('#openAll').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
switch (clickCount){
    case 1:
            $('#folder-684b3e0f-2876-4eaa-849d-55175dcc82c3-iteration-0').removeClass('collapsed')
            $('#folder-collapse-684b3e0f-2876-4eaa-849d-55175dcc82c3-iteration-0').addClass('show')
        $('#openAll').html("Collapse Folders");
        break;
    case 2:
            $('#folder-684b3e0f-2876-4eaa-849d-55175dcc82c3-iteration-0').addClass('collapsed')
            $('#folder-collapse-684b3e0f-2876-4eaa-849d-55175dcc82c3-iteration-0').removeClass('show')
        $('#openAll').html("Expand Folders");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Show/Hide The Requests -->

<script>
$('#openAllRequests').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
switch (clickCount){
    case 1:
            $('#requests-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('collapsed')
            $('#collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('collapsed')
            $('#requests-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('show')
            $('#collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('show')
            $('#requests-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('collapsed')
            $('#collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('collapsed')
            $('#requests-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('show')
            $('#collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('show')
            $('#requests-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('collapsed')
            $('#collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('collapsed')
            $('#requests-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('show')
            $('#collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('show')
            $('#requests-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('collapsed')
            $('#collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('collapsed')
            $('#requests-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('show')
            $('#collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('show')
            $('#requests-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('collapsed')
            $('#collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('collapsed')
            $('#requests-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('show')
            $('#collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('show')
            $('#requests-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('collapsed')
            $('#collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('collapsed')
            $('#requests-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('show')
            $('#collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('show')
        $('#openAllRequests').html("Collapse Requests");
        break;
    case 2:
            $('#requests-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('collapsed')
            $('#collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('collapsed')
            $('#requests-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('show')
            $('#collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('show')
            $('#requests-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('collapsed')
            $('#collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('collapsed')
            $('#requests-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('show')
            $('#collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('show')
            $('#requests-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('collapsed')
            $('#collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('collapsed')
            $('#requests-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('show')
            $('#collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('show')
            $('#requests-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('collapsed')
            $('#collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('collapsed')
            $('#requests-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('show')
            $('#collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('show')
            $('#requests-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('collapsed')
            $('#collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('collapsed')
            $('#requests-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('show')
            $('#collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('show')
            $('#requests-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('collapsed')
            $('#collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('collapsed')
            $('#requests-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('show')
            $('#collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('show')
        $('#openAllRequests').html("Expand Requests");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Show/Hide The Skipped Tests -->

<script>
$('#openAllSkipped').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
switch (clickCount){
    case 1:
            $('#skipped-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('collapsed')
            $('#skipped-collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('collapsed')
            $('#skipped-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('show')
            $('#skipped-collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('show')
            $('#skipped-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('collapsed')
            $('#skipped-collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('collapsed')
            $('#skipped-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('show')
            $('#skipped-collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('show')
            $('#skipped-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('collapsed')
            $('#skipped-collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('collapsed')
            $('#skipped-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('show')
            $('#skipped-collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('show')
            $('#skipped-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('collapsed')
            $('#skipped-collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('collapsed')
            $('#skipped-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('show')
            $('#skipped-collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('show')
            $('#skipped-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('collapsed')
            $('#skipped-collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('collapsed')
            $('#skipped-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('show')
            $('#skipped-collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('show')
            $('#skipped-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('collapsed')
            $('#skipped-collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('collapsed')
            $('#skipped-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('show')
            $('#skipped-collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('show')
        $('#openAllSkipped').html("Collapse All Skipped Tests");
        break;
    case 2:
            $('#skipped-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('collapsed')
            $('#skipped-collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').addClass('collapsed')
            $('#skipped-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('show')
            $('#skipped-collapse-cb06e661-f9be-4e6b-8948-7aa470992e1b').removeClass('show')
            $('#skipped-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('collapsed')
            $('#skipped-collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').addClass('collapsed')
            $('#skipped-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('show')
            $('#skipped-collapse-5f24eaa1-00d5-4cca-8170-36b6d700d397').removeClass('show')
            $('#skipped-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('collapsed')
            $('#skipped-collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').addClass('collapsed')
            $('#skipped-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('show')
            $('#skipped-collapse-c4f25e75-8204-4483-9e19-ff7be8cffeac').removeClass('show')
            $('#skipped-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('collapsed')
            $('#skipped-collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').addClass('collapsed')
            $('#skipped-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('show')
            $('#skipped-collapse-ce340ea9-efe6-48ca-95e6-df0fcf5244f8').removeClass('show')
            $('#skipped-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('collapsed')
            $('#skipped-collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').addClass('collapsed')
            $('#skipped-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('show')
            $('#skipped-collapse-37b14767-e282-4a5f-a49b-60239c17d0a3').removeClass('show')
            $('#skipped-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('collapsed')
            $('#skipped-collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').addClass('collapsed')
            $('#skipped-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('show')
            $('#skipped-collapse-5abc7f8b-c989-4251-874a-e2fbbe8174b6').removeClass('show')
        $('#openAllSkipped').html("Expand All Skipped Tests");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Show/Hide The Failures -->

<script>
$('#openAllFailed').on('click', function(e) {
let clickCount = $(this).data("clickCount") || 1
let failedItemContent
let failedItemHeading
switch (clickCount){
    case 1:
        $('#openAllFailed').html("Collapse All Failed Tests");
        break;
    case 2:
        $('#openAllFailed').html("Expand All Failed Tests");
        break;
}
clickCount = clickCount > 1 ? 1 : ++clickCount;
$(this).data("clickCount", clickCount)
})
</script>

<!-- Pretty Print the Response Body-->

<script>
function isJSON(data)
{
    var ret = true;
    try {
            JSON.parse(data);
    }catch(e) {
            ret = false;
    }
    return ret;
}

function isXML(data)
{
    return (data.length > 0 && data[0] === '<');
}

// see https://gist.github.com/sente/1083506/d2834134cd070dbcc08bf42ee27dabb746a1c54d#gistcomment-2254622
function formatXML(data) {
    const PADDING = ' '.repeat(2); // set desired indent size here
    const reg = /(>)(<)(\/*)/g;
    let pad = 0;
    xml = data.replace(reg, '$1\r\n$2$3');

    return xml.split('\r\n').map((node, index) => {
        let indent = 0;
        if (node.match(/.+<\/\w[^>]*>$/)) {
            indent = 0;
        } else if (node.match(/^<\/\w/) && pad > 0) {
            pad -= 1;
        } else if (node.match(/^<\w[^>]*[^\/]>.*$/)) {
            indent = 1;
        } else {
            indent = 0;
        }

        pad += indent;
        return PADDING.repeat(pad - indent) + node;
    }).join('\r\n');
}

$(".prettyPrint").each(function () {
        var data = $(this).text();
        // Verify whether data is JSON
        if(isJSON(data))
        {
                obj = JSON.parse(data);
                data = JSON.stringify(obj, null, 2);
        }
        else if(isXML(data)) {
            data = formatXML(data);
        }
        $(this).text(data);
});
</script>


<!-- Copy Response Body To Clipboard -->

<script>
    var clipboard = new ClipboardJS('.copyButton');

    clipboard.on('success', function(e) {
        e.clearSelection();
        $(".copyButton").addClass("bg-success text-white")
        e.trigger.textContent = '✔ Copied!';
        window.setTimeout(function() {
            $(".copyButton").removeClass("bg-success text-white")
            e.trigger.textContent = 'Copy to Clipboard';
        }, 2000);
    });
    clipboard.on('error', function(e) {
        e.clearSelection();
        $(".copyButton").addClass("bg-danger text-white")
        e.trigger.textContent = '✗ Not Copied';
        window.setTimeout(function() {
            $(".copyButton").removeClass("bg-danger text-white")
            e.trigger.textContent = 'Copy to Clipboard';
        }, 2000);
    });

</script>

<!-- Render the Description Markdown and link in the test failures -->

<script>
    const remarkable = new Remarkable();

    const descriptions = document.querySelectorAll(".renderMarkdown");
    descriptions.forEach(description => {
        description.innerHTML = renderHtmlFromMarkdown(description.textContent);
    });
    function renderHtmlFromMarkdown(markdown) {
        return remarkable.render(trim(markdown));
    }
    function trim(string) {
        return string ? string.replace(/^ +| +$/gm, "") : string;
    }
</script>

<!-- Show/Hide The Toggles When Scrolling The Page -->

<script>
window.onscroll = function() {scrollFunction()};

function scrollFunction() {
  if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
    document.getElementById("topOfRequestsScreen").style.display = "block";
    document.getElementById("topOfFailuresScreen").style.display = "block";
    document.getElementById("topOfSkippedScreen").style.display = "block";
    document.getElementById("openAll").style.display = "none";
    document.getElementById("openAllRequests").style.display = "none";


  } else {
    document.getElementById("topOfRequestsScreen").style.display = "none";
    document.getElementById("topOfFailuresScreen").style.display = "none";
    document.getElementById("topOfSkippedScreen").style.display = "none";
    document.getElementById("openAll").style.display = "block";
    document.getElementById("openAllRequests").style.display = "block";

  }
}

function topFunction() {
  document.body.scrollTop = 0;
  document.documentElement.scrollTop = 0;
}
</script>

<!-- Creates The Iteration Tabs -->

<script type="text/javascript">
    "use strict";

window.onload = function () {

  // set display for all blocks of response
  var allItems = document.querySelectorAll('[class*=iteration-]');
  allItems.forEach(function(elem){
    elem.style.display = 'block';
  });

   
  let totalIterations = 1;
   

  let menu = document.querySelector('#execution-menu .nav');

  for(var i = 0; i < totalIterations; i++)
  {
    let li = document.createElement('li');
    li.appendChild(document.createTextNode((i + 1)));
    li.setAttribute('id', 'iteration-' + i);
    li.classList.add("custom-tab");
    li.classList.add("itPassed");

    li.addEventListener('click', function() {
      //set display to none for all except row
      let allItems = document.querySelectorAll('[class*=iteration-]:not(.row)');
      allItems.forEach(function(elem) {
        elem.style.display = 'none';
      })

      let allMenus = document.querySelectorAll('[id*=iteration-]');
      allMenus.forEach(function(elem){
        elem.style.borderBottom = 'none';
      })

      this.style.borderBottom = 'solid 3px #032a33';

      let items = document.querySelectorAll("." + this.id + ':not(.row)');
      items.forEach(function(elem) {
        elem.style.display = elem.style.display == 'block' ? 'none' : 'block';
      })
    });
    menu.appendChild(li);
  }

  //shows first tab data
  document.getElementById('iteration-0').click();
  document.getElementById('iterationSelected').innerHTML = `Iteration ${document.getElementById('iteration-0').innerHTML} selected`

}
</script>

<!-- Create the Selected Iteration Label -->

<script>
$(document).ready(function(){
    $(function() {
        $("#iterationList li").click(function() {
            document.getElementById('iterationSelected').innerHTML = "Iteration " + this.innerHTML + " selected"
        });
    });
});
</script>

<!-- Filter Action for the Iterations -->

<script>
$("#filterInput").on("input paste", function() {
    var value = $(this).val();
    $("#iterationList li").filter(function() {
	    $("#showOnlyFailures").data("clickCount") ? $("#showOnlyFailures").click():null;
        $(this).toggle($(this).text().indexOf(value) > -1)
    });
});
</script>

<!-- Showing the Failed Interations -->

<script>
$('#showOnlyFailures').on('click', function(e) {
    let clickCount = $(this).data("clickCount") || 1
	$("#filterInput").val()!="" && clickCount==1 ? $("#filterInput").val('').trigger('input'): null;
    let selectedIteration = $('#iterationList li').filter(function () {
        return $(this).css('border-bottom').indexOf("solid") > -1 && $(this).hasClass('itFailed');
    });
    selectedIteration.length || clickCount > 1 ? null : $("#iterationList li.itFailed")[0].click()
    $("#iterationList li.itPassed").toggle()
    $("div.bg-success [id*=requests]").parents('[class^="row iteration-"]').toggle();
    clickCount = clickCount > 1 ? 1 : ++clickCount;
    clickCount > 1 ? $("#showOnlyFailures").html("Show All Iterations") : $("#showOnlyFailures").html("Show Failed Iterations");
    $(this).data("clickCount", clickCount)
})
</script>
</body>
</html>
