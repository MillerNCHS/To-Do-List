<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "todo = [&quot;clean basement&quot;, &quot;change oil in truck&quot;,&quot;wax skis &amp; board&quot;,&quot;buy christmas gift&quot;]\n" +
    "moretasks = &quot;&quot;\n" +
    "while (moretasks != &quot;done&quot;):\n" +
    "    moretasks = input(&quot;What is another task to add to you todo list (done to stop)&quot;)\n" +
    "    todo.append(moretasks)\n" +
    "    \n" +
    "print(&quot;Your todo list for the weekend is:&quot;)\n" +
    "for task in todo:\n" +
    "    print (task)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
