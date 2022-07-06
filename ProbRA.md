
```mermaid
flowchart TD
  Exposure_Ext-->Absortion
  Absortion-->Systemic_Circulation
  Systemic_Circulation-->Tissue
  Tissue-->Exposure_Int
```

var mermaidAPI = mermaid.mermaidAPI;

mermaidAPI.initialize({
  startOnLoad:false
});

var element = document.getElementById("app");
var insertSvg = function(svgCode, bindFunctions) {
  element.innerHTML = svgCode;
};
var graphDefinition = `graph LR; Systemstart-->SomeIcon(<img src='https://iconscout.com/ms-icon-310x310.png' width='40' height='40' />)`;
var graph = mermaidAPI.render("mermaid", graphDefinition, insertSvg);

