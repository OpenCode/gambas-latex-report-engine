Latex Report Engine
==========================

A report engine for Gambas language created to generate dvi or pdf report with latex syntax

To create a report you must use preconfigured functions.

Example for a simple report:

    Dim parser As LatexReportEngine
    Dim features As LatexReportEngineList

    parser = New LatexReportEngine("latex_report")

    ' ----- Define standard document parameters
    parser.DocumentClass()  'Required
    ' ----- Open the report
    parser.Begin() 'Required
    ' ----- Create a page with title
    parser.SetTitle("Latex Report Engine", "Francesco Apruzzese", "2014-05-30")
    ' ----- Insert some text
    parser.InsertText("This is a Report Engine for Gambas Language based on " & parser.Latex & " syntax")
    parser.InsertText(parser.LineBreak)
    ' ----- Insert list
    parser.InsertText("Some Features:")
    features = New LatexReportEngineList("", ["Title", "Basic Report Creating", "List Management"])
    features.SetType(features.Itemize)
    parser.IncludeElement(features)
    ' ----- Close the report
    parser.End() 'Required
    ' ----- Actual report content
    Print parser.GetContent()
    ' ----- Parse the report in a PDF file
    parser.Parsing(parser.FormatPdf)
    ' ----- Open the report
    Desktop.Open(parser.GetReportPath() &/ parser.GetReportName() & ".pdf")

The functions DocumentClass() and Begin() are required first of all other functions and End() is the last function to call before the parsing.

DEPENDENCIES
==========================

Latex Report Engine need 'latex' and 'pdflatex' to generate the final report. If you need to obtain the report in dvi or pdf format you must install this softwares.

DOCS
==========================

Visit the [WIKI](https://github.com/OpenCode/gambas-latex-report-engine/wiki) for documentation
