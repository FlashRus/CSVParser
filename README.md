# CSVParser
Delphi Simple CSV Parser with no memory leak. Load CSV Data and start processing it.

# Usage :
Add csvparser.pas on delphi IDE library

Create only one instance of TCSVParser on programm start: ParseCsv := TCSVParser.Create;
```
uses CSVParser;

var ParseCsv: TCSVParser;
begin
  
  try
    ParseCsv.SetDataFile := 'your\directory\example.csv';
    ParseCsv.Open;

    while not ParseCsv.Eof do
    begin
      Memo1.Lines.Add(ParseCsv.Fields[5]); //or ParseCsv.FieldByName['column_name']
      ParseCsv.Next;
    end;
    
  finally
    ParseCsv.Clear; //clear all of used StringLists
  end;
end;
```

Available properties and methods :
* property SetDataFile - Set csv directori file
* property SetDelimiter - For ddefault ','
* property Fields - result string from Index of column
* property FieldByName - result string from Name of column
and others read source
