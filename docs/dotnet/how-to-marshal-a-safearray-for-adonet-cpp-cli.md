---
title: "Wie: Marshallen eines SAFEARRAY für ADO.NET (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 397312a5cc8ef4869f5ce8576e5787e141c1a414
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-a-safearray-for-adonet-ccli"></a>Gewusst wie: Marshallen eines SAFEARRAY für ADO.NET (C++/CLI)
Veranschaulicht das Hinzufügen ein systemeigenen `SAFEARRAY` mit einer Datenbank und Gewusst wie: Marshallen ein verwaltetes Arrays aus einer Datenbank in ein natives `SAFEARRAY`.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse eine systemeigene C++ `class` (verglichen mit einer `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von systemeigenem Code verwendet werden soll, und verwaltete Typen in systemeigenem Code nicht verwendet werden können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).  
  
 Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [wie: Deklarieren Sie in systemeigenen Typen behandelt](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code aus, wie durch angezeigt wird der `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass systemeigene `SAFEARRAY` Typen werden als Werte für die Datenbankspalte ArrayIntsCol übergeben wird. Innerhalb der DatabaseClass diese `SAFEARRAY` Typen gemarshallt werden verwaltete Objekte, die mit dem Marshalling-Funktionalität der <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.Copy%2A> wird verwendet, um das Marshallen eine `SAFEARRAY` in ein verwaltetes Array von ganzen Zahlen und die Methode <xref:System.Runtime.InteropServices.Marshal.Copy%2A> wird verwendet, um ein verwaltetes Array von ganzen Zahlen zu marshallen eine `SAFEARRAY`.  
  
```  
// adonet_marshal_safearray.cpp  
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
  
    void AddRow(SAFEARRAY *arrayIntsColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        int len = arrayIntsColValue->rgsabound[0].cElements;  
        array<int> ^arr = gcnew array<int>(len);  
  
        int *pData;  
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);  
        Marshal::Copy(IntPtr(pData), arr, 0, len);  
        SafeArrayUnaccessData(arrayIntsColValue);  
  
        row["ArrayIntsCol"] = arr;  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",  
            Type::GetType("System.Int32[]"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,  
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
            // Marshal each column value from a managed array  
            // of Int32s to a SAFEARRAY of type VT_I4.  
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);  
            int *pData;  
            SafeArrayAccessData(values[i], (void **)&pData);  
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,  
                IntPtr(pData), 10);  
            SafeArrayUnaccessData(values[i]);  
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
  
    // Create a standard array.  
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
    // Create a SAFEARRAY.  
    SAFEARRAY *psa;  
    psa = SafeArrayCreateVector(VT_I4, 0, 10);  
  
    // Copy the data from the original array to the SAFEARRAY.  
    int *pData;  
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);  
    memcpy(pData, &originalArray, 40);  
    SafeArrayUnaccessData(psa);  
    db->AddRow(psa);  
  
    // Now retrieve the rows and display their contents.  
    SAFEARRAY *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ArrayIntsCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        int *pData;  
        SafeArrayAccessData(values[i], (void **)&pData);  
        for (int j = 0; j < 10; j++)  
        {  
            cout << pData[j] << " ";  
        }  
        cout << endl;  
        SafeArrayUnaccessData(values[i]);  
  
        // Deallocate the memory allocated using  
        // SafeArrayCreateVector.  
        SafeArrayDestroy(values[i]);  
    }  
  
    SafeArrayDestroy(psa);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei namens adonet_marshal_safearray.cpp, und geben Sie die folgende Anweisung aus:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET-Anwendungen](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Datenzugriff mit ADO.NET (C + c++ / CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Interoperabilität](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)