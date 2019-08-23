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






javascript part>----


document.getElementById('issueInputForm').addEventListener('submit',saveIssue);

function saveIssue(e) {
  var issueDesc= document.getElementById('issueDescInput').value;
  var issueSeverity=document.getElementById('issueSeverityInput').value;
  var issueAssignedTo=document.getElementById('issueAssigntoInput').value;
  var issueId =chance.guid();
  var issueStatus ='open';

  var issue = {
  id: issueId,
  description:issueDescription,
  assignedTo:issueAssignedTo,
  severity:issueSeverity,
  status:issueStatus
  }
  if(localStorage.getItems('issues')==null){
     var issues=[];
     issues.push(issue);
     localStorage.setItems('issues',JASON.stringify(issues))
   }else {
     var issues= JASON.parse(localStorage.getItems('issues'));
     issues.push(issue);
     localStorage.setItems('issues',JASON.stringify(issues));
   }
   document.getElementById('issueInputForm').reset();
   fetchIssues();
   e.preventDefault();
}

function fetchIssues(){

var issues = JASON.parse(localStorage.getItems('issues'));
var listIssues = document.getElementById('listIssues');

listIssues.innerHTML='';

for( var i=0 ; i<issues.length;i++){

var id= issues[i].id;
var des= issues[i].Description;
var severity=issues[i].severity;
var assignTo=issues[i].assignTo;
var status =issues[i].status;

issuesList.innerHTML+='<div class="well">'+
'<h6> Issues ID' +id+ '<h6>' +
'<p><span class="label label-info">' +status+ '</span></p>'+
'<h3>'+desc+'<h3>'+
'<p><span class="glyficon glyficon-time">'+severity+'</span></p>'+
'<p><span class="glyficon glyficon-user">'+assignTo+'</span></p>'+
'<a href="#" onClick="setStatusClosed(\''+id+'\')" class="btn btn-warning">close</a>'+
'<a  href ="#" onClick=deleteIssues(\''+id+'\') class ="btn btn-danger">delete</a>'+
'</div>'

}


}
