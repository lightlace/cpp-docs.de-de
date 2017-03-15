---
title: "Gewusst wie: Marshallen von Unicode-Zeichenfolgen f&#252;r ADO.NET (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], Marshallen von Unicode-Zeichenfolgen"
  - "Zeichenfolgen [C++], Unicode"
  - "Unicode [C++], Zeichenfolgen"
ms.assetid: 1da090ff-6b53-40be-841f-dc79dfe8ba10
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen von Unicode-Zeichenfolgen f&#252;r ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Veranschaulicht das Hinzufügen einer systemeigenen Unicode\-Zeichenfolge \(`wchar_t *`\) zu einer Datenbank und das Marshallen einer <xref:System.String?displayProperty=fullName> aus einer Datenbank in eine systemeigene Unicode\-Zeichenfolge.  
  
## Beispiel  
 In diesem Beispiel wird die Klasse DatabaseClass erstellt, die mit einem ADO.NET\-<xref:System.Data.DataTable>\-Objekt interagiert.  Beachten Sie, dass diese Klasse eine systemeigene C\+\+\-`class` ist \(im Vergleich zu einer `ref class` oder einer `value class`\).  Dies ist notwendig, weil wir diese Klasse von systemeigenem Code aus verwenden möchten und verwaltete Typen in systemeigenem Code nicht verwendet werden können.  Diese Klasse wird mit der CLR als Ziel kompiliert. Dies wird durch die der Klassendeklaration vorangestellte `#pragma managed`\-Direktive angezeigt.  Weitere Informationen über diese Direktive finden Sie unter [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Beachten Sie den privaten Member der DatabaseClass\-Klasse: `gcroot<DataTable ^> table`.  Da systemeigene Typen keine verwalteten Typen enthalten können, ist das `gcroot`\-Schlüsselwort erforderlich.  Weitere Information zu `gcroot` finden Sie unter [Gewusst wie: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Bei dem übrigen Code in diesem Beispiel handelt es sich um systemeigenen C\+\+\-Code, was durch die `#pragma unmanaged`\-Direktive vor `main` angezeigt wird.  In diesem Beispiel erstellen wir eine neue Instanz von DatabaseClass und rufen ihre Methoden auf, um eine Tabelle zu erstellen und einige Zeilen darin zu füllen.  Beachten Sie, dass Unicode\-C\+\+\-Zeichenfolgen als Werte für die Datenbankspalte StringCol übergeben werden.  Innerhalb der DatabaseClass werden diese Zeichenfolgen mit der Marshalling\-Funktionalität des <xref:System.Runtime.InteropServices?displayProperty=fullName>\-Namespaces in verwaltete Zeichenfolgen gemarshallt.  Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni*> zum Marshallen einer `wchar_t *` in eine <xref:System.String> und die Methode <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni*> zum Marshallen einer <xref:System.String> in eine `wchar_t *` verwendet.  
  
> [!NOTE]
>  Der durch <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni*> belegte Arbeitsspeicher muss durch Aufrufen von <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal*> oder `GlobalFree` freigegeben werden.  
  
```  
// adonet_marshal_string_wide.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(wchar_t *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringUni(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a wchar_t *.  
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
    db->AddRow(L"This is string 1.");  
    db->AddRow(L"This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    wchar_t *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalUni.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
  **StringCol: Hierbei handelt es sich um Zeichenfolge 1.**  
**StringCol: Hierbei handelt es sich um Zeichenfolge 2.**   
## Kompilieren des Codes  
  
-   Um den Code über die Kommandozeile zu kompilieren, speichern Sie das Codebeispiel in einer Datei mit dem Namen adonet\_marshal\_string\_wide.cpp, und geben Sie die folgende Anweisung ein:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp  
    ```  
  
## .NET Framework-Sicherheit  
 Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET\-Anwendungen](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Datenzugriff](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](assetId:///afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)