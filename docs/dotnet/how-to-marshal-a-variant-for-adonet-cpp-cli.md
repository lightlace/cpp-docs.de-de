---
title: "Wie: Marshallen eines VARIANT für ADO.NET (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 504f9553b85acefa085a7a8d6c85768ff934bab7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-a-variant-for-adonet-ccli"></a>Gewusst wie: Marshallen eines VARIANT für ADO.NET (C++/CLI)
Veranschaulicht das Hinzufügen ein systemeigenen `VARIANT` mit einer Datenbank und das Marshallen einer <xref:System.Object?displayProperty=fullName> aus einer Datenbank in ein natives `VARIANT`.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse eine systemeigene C++ `class` (verglichen mit einer `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von systemeigenem Code verwendet werden soll, und verwaltete Typen in systemeigenem Code nicht verwendet werden können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).  
  
 Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [wie: Deklarieren Sie in systemeigenen Typen behandelt](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code aus, wie durch angezeigt wird der `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass systemeigene `VARIANT` Typen werden als Werte für die Datenbankspalte ObjectCol übergeben wird. Innerhalb der DatabaseClass diese `VARIANT` Typen gemarshallt werden verwaltete Objekte, die mit dem Marshalling-Funktionalität der <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Insbesondere die Methode <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> wird verwendet, um das Marshallen eine `VARIANT` auf eine <xref:System.Object>, und die Methode <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> zum Marshallen ein <xref:System.Object> auf eine `VARIANT`.  
  
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
  
```Output  
ObjectCol: This is a BSTR in a VARIANT.  
ObjectCol: 42  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei namens adonet_marshal_variant.cpp, und geben Sie die folgende Anweisung aus:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET-Anwendungen](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Datenzugriff mit ADO.NET (C + c++ / CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Interoperabilität](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)