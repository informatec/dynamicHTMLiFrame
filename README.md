# Qlik Sense Jedox iFrame Window

This is a simple iFrame window that allows you to construct a dynamic URL to an external web service. A good example of this is connecting to the Windy.tv map service with the latitude longitude being passed dynamically based on selections in the application (See the example gif and the example QVF included in the Git download)

## Jedox Know How for passing variables

When using a report hyperlink in an external application, you can extend the hyperlink with settings for variables in the Jedox report, allowing you to pass information (e.g. “point of view” settings) from the external environment to the report.
A variable is addressed in a hyperlink by appending a parameter to the url in the form: 


**<report_link>&var/<variable_name>=<variable_value>**


For example, to pass this value 2015 to the variable @year, the following string needs to be appended: …&var/year=2015
It is possible to set values for multiple variables as well. Each further variable is simply appended with similar syntax.

Furthermore, you can also define multiple values for a single variable (in reports, the value type of this variable will then be an array), using the following syntax:

**…&var/year[]=2015&var/year[]=2016&var/year[]=2017…**


<br>
<img src="https://github.com/informatec/dynamicHTMLiFrame/blob/master/img/1.gif">
<br>

## Sample for passing url

**='http://localhost/ui/lnk/?_=eJxNj8EKwjAMh...' & '&var/BUD_YEAR=' & only(DISTINCT BudYear)**

<h3>Points to note</h3>
<ul><li>You need to understand how to construct the dynamic string for the URL, see example application included with <b> $(..) </b>  sections where the dynamic content is added </li>
<li>The end format of the URL you enter should look like ='https://www.abc.com/...'<br>
Please note the = sign and the single quotes around the URL.</li>
</ul>
