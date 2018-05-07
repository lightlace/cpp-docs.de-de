---
title: 'Wie: Marshallen von Unicode-Zeichenfolgen für ADO.NET (C + c++ / CLI) | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
ms.assetid: 1da090ff-6b53-40be-841f-dc79dfe8ba10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 15cf9e9806c0820ea5a410a93419016c2f678c65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-unicode-strings-for-adonet-ccli"></a>Gewusst wie: Marshallen von Unicode-Zeichenfolgen für ADO.NET (C++/CLI)
Veranschaulicht das Hinzufügen einer systemeigenen Unicode-Zeichenfolge (`wchar_t *`) mit einer Datenbank und das Marshallen einer <xref:System.String?displayProperty=fullName> aus einer Datenbank in eine systemeigene Unicode-Zeichenfolge.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse eine systemeigene C++ `class` (verglichen mit einer `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von systemeigenem Code verwendet werden soll, und verwaltete Typen in systemeigenem Code nicht verwendet werden können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).  
  
 Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [wie: Deklarieren Sie in systemeigenen Typen behandelt](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code aus, wie durch angezeigt wird der `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass C++ Unicode-Zeichenfolgen als Werte für die Datenbankspalte StringCol übergeben werden. Innerhalb der DatabaseClass werden diese Zeichenfolgen mit der Marshalling-Funktionalität in verwaltete Zeichenfolgen gemarshallt der <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Insbesondere die Methode <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> wird verwendet, um das Marshallen eine `wchar_t *` auf eine <xref:System.String>, und die Methode <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> wird verwendet, um das Marshallen eine <xref:System.String> auf eine `wchar_t *`.  
  
> [!NOTE]
>  Der vom zugeordneten Speicher <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> muss aufgehoben werden, durch den Aufruf eines <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> oder `GlobalFree`.  
  
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
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei namens adonet_marshal_string_wide.cpp, und geben Sie die folgende Anweisung aus:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET-Anwendungen](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Datenzugriff mit ADO.NET (C + c++ / CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Interoperabilität](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)