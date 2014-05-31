gambas-latex-report-engine
==========================

A report engine for Gambas language created to generate dvi or pdf report with latex syntax

To create a report you must just use the preconfigured functions.

Example for a simple report:

    Dim parser As LatexReportEngine
    
    parser = New LatexReportEngine("prova")

    ' ----- Define standard document parameters
    parser.DocumentClass()  'Required
    ' ----- Open the report
    parser.Begin() 'Required
    ' ----- Create a page with title
    parser.SetTitle("La prova", "Francesco Apruzzese", "2014-05-30")
    ' ----- Close the report
    parser.End() 'Required
    ' ----- Parse the report in a PDF file
    parser.Parsing(parser.FormatPdf)
    
The functions DocumentClass() and Begin() are required first of all other functions and End() is the last function to call before the parsing.
