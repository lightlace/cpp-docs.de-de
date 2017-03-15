---
title: "Gewusst wie: Marshallen eines VARIANT f&#252;r ADO.NET (C++/CLI)"
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
  - "ADO.NET [C++], Marshallen von VARIANT-Typen"
  - "VARIANT"
  - "VARIANT, Marshalling"
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen eines VARIANT f&#252;r ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Veranschaulicht das Hinzufügen eines systemeigenen `VARIANT`\-Datentyps zu einer Datenbank und das Marshallen einer <xref:System.Object?displayProperty=fullName>\-Zeichenfolge aus einer Datenbank in einen systemeigenen `VARIANT`\-Datentyp.  
  
## Beispiel  
 In diesem Beispiel wird die Klasse DatabaseClass erstellt, die mit einem ADO.NET\-<xref:System.Data.DataTable>\-Objekt interagiert.  Beachten Sie, dass diese Klasse eine systemeigene C\+\+\-`class` ist \(im Vergleich zu einer `ref class` oder einer `value class`\).  Dies ist notwendig, weil wir diese Klasse von systemeigenem Code aus verwenden möchten und verwaltete Typen in systemeigenem Code nicht verwendet werden können.  Diese Klasse wird mit der CLR als Ziel kompiliert. Dies wird durch die der Klassendeklaration vorangestellte `#pragma managed`\-Direktive angezeigt.  Weitere Informationen über diese Direktive finden Sie unter [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Beachten Sie den privaten Member der DatabaseClass\-Klasse: `gcroot<DataTable ^> table`.  Da systemeigene Typen keine verwalteten Typen enthalten können, ist das `gcroot`\-Schlüsselwort erforderlich.  Weitere Information zu `gcroot` finden Sie unter [Gewusst wie: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Bei dem übrigen Code in diesem Beispiel handelt es sich um systemeigenen C\+\+\-Code, was durch die `#pragma unmanaged`\-Direktive vor `main` angezeigt wird.  In diesem Beispiel erstellen wir eine neue Instanz von DatabaseClass und rufen ihre Methoden auf, um eine Tabelle zu erstellen und einige Zeilen darin zu füllen.  Beachten Sie, dass systemeigene `VARIANT`\-Typen als Werte für die Datenbankspalte ObjectCol übergeben werden.  Innerhalb der DatabaseClass werden diese `VARIANT`\-Typen mit der Marshalling\-Funktionalität des <xref:System.Runtime.InteropServices?displayProperty=fullName>\-Namespaces in verwaltete Objekte gemarshallt.  Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant*> zum Marshallen eines `VARIANT` in ein <xref:System.Object> und die Methode <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject*> zum Marshallen eines <xref:System.Object> in einen `VARIANT` verwendet.  
  
```  
// adonet_marshal_variant.cpp  
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
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
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
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
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
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
  **ObjectCol: Dies ist ein BSTR in einer VARIANTE.**  
**ObjectCol: 42**   
## Kompilieren des Codes  
  
-   Um den Code über die Kommandozeile zu kompilieren, speichern Sie das Codebeispiel in einer Datei mit dem Namen adonet\_marshal\_variant.cpp, und geben Sie die folgende Anweisung ein:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## .NET Framework-Sicherheit  
 Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET\-Anwendungen](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Datenzugriff](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](assetId:///afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)