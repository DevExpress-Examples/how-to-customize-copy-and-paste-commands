<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128609846/24.2.1%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E3665)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
# How to: Customize Copy and Paste Commands

This example illustrates how to use the [IRichEditCommandFactoryService](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.Services.IRichEditCommandFactoryService) service substitution to override <code>CopySelectionCommand</code> and <code>PasteSelectionCommand</code> behavior.

## Implementation Details

Customized <code>CopySelectionCommand</code> copies selection to the [Clipboard](https://learn.microsoft.com/en-us/dotnet/api/system.windows.clipboard) in [HTML Clipboard Format](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767917(v=vs.85)) (see the <code>HtmlHelper.GetHtmlClipboardFormat()</code> method). This allows you to copy the RichEditControl content and paste it directly to a control that can accept HTML-formatted data from the Clipboard (e. g. [ASPxHtmlEditor](https://docs.devexpress.com/AspNet/DevExpress.Web.ASPxHtmlEditor.ASPxHtmlEditor)). Note that images are embedded into the resulting HTML according to the [Data URI scheme](http://en.wikipedia.org/wiki/Data_URI_scheme) specification to avoid dependency on the image location (it may not be resolved by the target application).

> **Note:**
>
> Starting with **v20.2.5**, RichEditControl supports copying data in the HTML Clipboard format. To enable this functionality, use the [ClipboardFormats.Html](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.DataFormatOptions.Html) option.
  
The customized <code>PasteSelectionCommand</code> retrieves plain (unformatted) text from the Clipboard and pastes this text into the RichEditControl.

## Files to Review

* [Form1.cs](./CS/RichEditCustomCopyPaste/Form1.cs) (VB: [Form1.vb](./VB/Form1.vb))
* [CustomCommands.cs](./CS/RichEditCustomCopyPaste/CustomCommands.cs) (VB: [CustomCommands.vb](./VB/CustomCommands.vb))
* [HtmlRelatedClasses.cs](./CS/RichEditCustomCopyPaste/HtmlRelatedClasses.cs) (VB: [HtmlRelatedClasses.vb](./VB/HtmlRelatedClasses.vb))

## More Examples

* [How to replace standard XtraRichEdit command with a custom command](https://github.com/DevExpress-Examples/how-to-replace-standard-xtrarichedit-command-with-your-own-custom-command-e2224)

## Documentation

* [Commands in Rich Text Editor](https://docs.devexpress.com/WindowsForms/9328/controls-and-libraries/rich-text-editor/commands)
* [How to: Bind a Command to a Button in the Rich Text Editor for WinForms](https://docs.devexpress.com/WindowsForms/7071/controls-and-libraries/rich-text-editor/examples/commands/how-to-bind-a-command-to-a-button)
* [How to: Replace a Built-In Command with a Custom Command in Rich Text Editor for WinForms](https://docs.devexpress.com/WindowsForms/113758/controls-and-libraries/rich-text-editor/examples/commands/how-to-customize-built-in-command-using-service-substitution)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=how-to-customize-copy-and-paste-commands&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=how-to-customize-copy-and-paste-commands&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
