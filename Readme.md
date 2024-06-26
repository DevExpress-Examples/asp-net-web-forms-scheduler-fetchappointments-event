<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128546743/13.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E489)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [Default.aspx](./CS/Default.aspx) (VB: [Default.aspx](./VB/Default.aspx))
* [Default.aspx.cs](./CS/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/Default.aspx.vb))
<!-- default file list end -->
# How to enhance performance when handling a large number of appointments


<p>Problem:</p><p>The Scheduler behaves perfectly well when there is a reasonable amount of appointments to display. However, what if I am required to handle large appointment datasets? If I use the ObjectDataSource, then all data are loaded when a page is being created. That means that the application is fetching unnecessary data, increasing server workload and degrading the overall performance. It is suggested that in this case the FetchAppointments event should be used to narrow the time frame for which appointments should be retrieved. However, how does one get the newly selected time interval in the page cycle before the ObjectDataSource retrieves data from the underlying data source?</p><p>Solution:</p><p>This example illustrates the use of the FetchAppointments event to limit the number of appointments loaded at a time to the appointments actually shown. To achieve this, a new data source control is created by using the ObjectDataSource. This control implements its own CRUD procedures for appointment and resources. It enables you to intercept requests for visible interval changes and load only necessary data.<br />
Note that page rendering performance is highly affected by the browser type. Internet Explorer seems to be the slowest one, so it is recommended to view the example using FireFox.</p><p>P.S. If you run this example online, the scheduler is in read-only mode, so no modifications or new appointment insertion are allowed.</p>

<br/>


<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=asp-net-web-forms-scheduler-fetchappointments-event&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=asp-net-web-forms-scheduler-fetchappointments-event&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
