# Medical-Issues-RECORD
This software helps doctors to easily record the issues of their patient.
HTML.

<title>DREAMIX CODE</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  </head>

  <body onload="fetchIssues()">
    <div class="container">
      <h1>JEAN-PAUL BOGA <small> THE Smart coder mister JAY</small></h1>
      <div class="jumbotron">
        <h1>add new issue</h1>
        <form id="issueInputForm">

           <div class="form-group">
             <label for="issueDescriptionInput">Description</label>
             <input type="text" class="form-controller" id="issueDecInput" placeholder="isue Description">
           </div>

           <div class="<form-group">
              <label for="issueSeverityInput">  Severity</label>
              <select id="issueSeverityInput">
                <option value="low">Low</option>
                <option value="medium">Medium</option>
                <option value="high">Hight</option>
              </select>
              <div class="form-group">
                <label for="issueInputAssignto">Assign to</label>
                <input type="text" class="form-controller" id="issueInputAssignto" placeholder="Enter Responsible">
              </div>
           </div>
           <button type="submit" class="btn btn-primary">Add</button>
       </form >
    </div>
    <div class="col-lg-12">
      <div ="ListIssue">
      </div>
      <div class="footer">
        <p>&copy Brightchrisolythcoding.onix </p>
      </div>

    </div>
    </div>



    <script scr="https://chancejs.com/chance.min.js">
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="main.js">

    </script>
  </body>
</html>
