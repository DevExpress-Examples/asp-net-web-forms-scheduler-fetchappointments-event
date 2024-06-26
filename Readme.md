<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128546743/17.1.9%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E489)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->

# Scheduler for ASP.NET Web Forms - How to enhance scheduler performance when handling a large number of appointments

This example demonstrates how to handle the [FetchAppointments](https://docs.devexpress.com/AspNet/DevExpress.Web.ASPxScheduler.ASPxSchedulerDataWebControlBase.FetchAppointments) event to dynamically limit the number of appointments loaded into the scheduler storage. This approach can be useful when a scheduler contains a large amount of data, and only a small part of it needs to be loaded at one time.

```csharp
protected void ASPxScheduler1_FetchAppointments(object sender, DevExpress.XtraScheduler.FetchAppointmentsEventArgs e) {
    SetAppointmentDataSourceSelectCommandParameters(e.Interval);
    e.ForceReloadAppointments = true;
}
protected void SetAppointmentDataSourceSelectCommandParameters(TimeInterval interval) {
    SqlDataSource1.SelectParameters["OriginalOccurrenceStart"].DefaultValue = interval.Start.ToString();
    SqlDataSource1.SelectParameters["OriginalOccurrenceEnd"].DefaultValue = interval.End.ToString();
}
```

## Files to Review

* [Default.aspx](./CS/Default.aspx) (VB: [Default.aspx](./VB/Default.aspx))
* [Default.aspx.cs](./CS/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/Default.aspx.vb))

## Documentation

* [FetchAppointments Event - Handling Large Datasets](https://docs.devexpress.com/WindowsForms/8385/controls-and-libraries/scheduler/data-binding/fetchappointments-event-handling-large-datasets)
  
## More Examples

* [Scheduler for ASP.NET MVC - - How to implement the FetchAppointment delegate method](https://github.com/DevExpress-Examples/asp-net-mvc-scheduler-fetch-appointment-event)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=asp-net-web-forms-scheduler-fetchappointments-event&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=asp-net-web-forms-scheduler-fetchappointments-event&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
