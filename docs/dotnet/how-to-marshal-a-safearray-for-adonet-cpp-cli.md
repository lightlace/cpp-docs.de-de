---
title: "Gewusst wie: Marshallen eines SAFEARRAY f&#252;r ADO.NET (C++/CLI)"
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
  - "ADO.NET [C++], Marshallen von SAFEARRAY-Typen"
  - "SAFEARRAY, Marshalling"
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Marshallen eines SAFEARRAY f&#252;r ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Veranschaulicht, wie ein systemeigenes `SAFEARRAY` einer Datenbank hinzugefügt und ein verwaltetes Array aus einer Datenbank in ein systemeigenes `SAFEARRAY` gemarshallt wird.  
  
## Beispiel  
 In diesem Beispiel wird die Klasse DatabaseClass erstellt, die mit einem ADO.NET\-<xref:System.Data.DataTable>\-Objekt interagiert.  Beachten Sie, dass diese Klasse eine systemeigene C\+\+\-`class` ist \(im Vergleich zu einer `ref class` oder einer `value class`\).  Dies ist notwendig, weil wir diese Klasse von systemeigenem Code aus verwenden möchten und verwaltete Typen in systemeigenem Code nicht verwendet werden können.  Diese Klasse wird mit der CLR als Ziel kompiliert. Dies wird durch die der Klassendeklaration vorangestellte `#pragma managed`\-Direktive angezeigt.  Weitere Informationen über diese Direktive finden Sie unter [managed, unmanaged](../preprocessor/managed-unmanaged.md).  
  
 Beachten Sie den privaten Member der DatabaseClass\-Klasse: `gcroot<DataTable ^> table`.  Da systemeigene Typen keine verwalteten Typen enthalten können, ist das `gcroot`\-Schlüsselwort erforderlich.  Weitere Information zu `gcroot` finden Sie unter [Gewusst wie: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Bei dem übrigen Code in diesem Beispiel handelt es sich um systemeigenen C\+\+\-Code, was durch die `#pragma unmanaged`\-Direktive vor `main` angezeigt wird.  In diesem Beispiel erstellen wir eine neue Instanz von DatabaseClass und rufen ihre Methoden auf, um eine Tabelle zu erstellen und einige Zeilen darin zu füllen.  Beachten Sie, dass systemeigene `SAFEARRAY`\-Typen als Werte für die Datenbankspalte ArrayIntsCol übergeben werden.  Innerhalb der DatabaseClass werden diese `SAFEARRAY`\-Typen mithilfe der Marshalling\-Funktionalität des <xref:System.Runtime.InteropServices?displayProperty=fullName>\-Namespaces in verwaltete Objekte gemarshallt.  Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.Copy*> zum Marshallen eines `SAFEARRAY` in ein verwaltetes Array mit ganzen Zahlen verwendet, und die Methode <xref:System.Runtime.InteropServices.Marshal.Copy*> wird zum Marshallen eines verwalteten Arrays mit ganzen Zahlen in ein `SAFEARRAY` verwendet.  
  
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
  
  **0 1 2 3 4 5 6 7 8 9**    
## Kompilieren des Codes  
  
-   Um den Code über die Kommandozeile zu kompilieren, speichern Sie das Codebeispiel in einer Datei mit dem Namen adonet\_marshal\_safearray.cpp, und geben Sie die folgende Anweisung ein:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## .NET Framework-Sicherheit  
 Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET\-Anwendungen](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Datenzugriff](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](assetId:///afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)