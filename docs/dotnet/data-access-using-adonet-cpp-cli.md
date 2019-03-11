---
title: Datenzugriff mit ADO.NET (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
- native strings [C++]
- ADO.NET [C++], marshaling ANSI strings
- strings [C++], ADO.NET
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
ms.openlocfilehash: b258e574b912b1c32e5ffae7ba29cfc5f9903685
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749346"
---
# <a name="data-access-using-adonet-ccli"></a>Datenzugriff mit ADO.NET (C++/CLI)

ADO.NET ist die .NET Framework-API für den Datenzugriff und bietet die Leistung und benutzerfreundlichkeit von vorherigen Data Access-Lösungen. Dieser Abschnitt beschreibt einige der Probleme im Zusammenhang mit ADO.NET, die in Visual C++-Benutzer, z. B. das Marshalling systemeigenen Typs sind.

ADO.NET wird unter der Common Language Runtime (CLR) ausgeführt. Aus diesem Grund muss jede Anwendung, die Interaktion mit ADO.NET auch die CLR abzielen. Allerdings bedeutet dies nicht, dass native Anwendungen keine ADO.NET verwenden. Diese Beispiele zeige, wie für die Interaktion mit einer ADO.NET-Datenbank von systemeigenem Code.

## <a name="marshal_ansi"></a> Marshallen von ANSI-Zeichenfolgen für ADO.NET

Veranschaulicht, wie eine native Zeichenfolge hinzufügen möchten (`char *`) mit einer Datenbank und das Marshallen einer <xref:System.String?displayProperty=fullName> aus einer Datenbank in eine systemeigene Zeichenfolge.

### <a name="example"></a>Beispiel

In diesem Beispiel die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse ein systemeigenes C++ `class` (im Vergleich zu einem `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von nativem Code verwendet werden soll, und keine verwaltete Typen in systemeigenem Code können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie, die vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).

Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können nicht die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [Vorgehensweise: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).

Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code, gekennzeichnet durch die `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass systemeigene C++-Zeichenfolgen als Werte für die Datenbankspalte StringCol übergeben werden. Innerhalb der DatabaseClass diese Zeichenfolgen mit dem Marshalling-Funktionalität in verwaltete Zeichenfolgen gemarshallt werden die <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> zum Marshallen eine `char *` auf eine <xref:System.String>, und die Methode <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> zum Marshallen einer <xref:System.String> auf eine `char *`.

> [!NOTE]
>  Die Speichermenge von <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> muss aufgehoben werden, durch Aufrufen von entweder <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> oder `GlobalFree`.

```cpp
// adonet_marshal_string_native.cpp
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

    void AddRow(char *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringAnsi(
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

    int GetValuesForColumn(char *dataColumn, char **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringAnsi(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a char *.
            values[i] = (char *)Marshal::StringToHGlobalAnsi(
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
    db->AddRow("This is string 1.");
    db->AddRow("This is string 2.");

    // Now retrieve the rows and display their contents.
    char *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        "StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        cout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalAnsi.
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

### <a name="compiling-the-code"></a>Kompilieren des Codes

- Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei, die mit dem Namen adonet_marshal_string_native.cpp, und geben Sie die folgende Anweisung aus:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal_bstr"></a> Marshallen von BSTR-Zeichenfolgen für ADO.NET

Veranschaulicht das Hinzufügen eine COM-Zeichenfolge (`BSTR`) mit einer Datenbank und das Marshallen einer <xref:System.String?displayProperty=fullName> aus einer Datenbank in eine `BSTR`.

### <a name="example"></a>Beispiel

In diesem Beispiel die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse ein systemeigenes C++ `class` (im Vergleich zu einem `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von nativem Code verwendet werden soll, und keine verwaltete Typen in systemeigenem Code können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie, die vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).

Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können nicht die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [Vorgehensweise: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).

Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code, gekennzeichnet durch die `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass die COM-Zeichenfolgen als Werte für die Datenbankspalte StringCol übergeben werden. Innerhalb der DatabaseClass diese Zeichenfolgen mit dem Marshalling-Funktionalität in verwaltete Zeichenfolgen gemarshallt werden die <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> zum Marshallen eine `BSTR` auf eine <xref:System.String>, und die Methode <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> zum Marshallen einer <xref:System.String> auf eine `BSTR`.

> [!NOTE]
>  Die Speichermenge von <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> muss aufgehoben werden, durch Aufrufen von entweder <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> oder `SysFreeString`.

``` cpp
// adonet_marshal_string_bstr.cpp
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

    void AddRow(BSTR stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringBSTR(
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

    int GetValuesForColumn(BSTR dataColumn, BSTR *values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringBSTR(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a BSTR.
            values[i] = (BSTR)Marshal::StringToBSTR(
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

    BSTR str1 = SysAllocString(L"This is string 1.");
    db->AddRow(str1);

    BSTR str2 = SysAllocString(L"This is string 2.");
    db->AddRow(str2);

    // Now retrieve the rows and display their contents.
    BSTR values[MAXCOLS];
    BSTR str3 = SysAllocString(L"StringCol");
    int len = db->GetValuesForColumn(
        str3, values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        wcout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToBSTR.
        SysFreeString(values[i]);
    }

    SysFreeString(str1);
    SysFreeString(str2);
    SysFreeString(str3);
    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>Kompilieren des Codes

- Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei, die mit dem Namen adonet_marshal_string_native.cpp, und geben Sie die folgende Anweisung aus:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal_unicode"></a> Marshallen von Unicode-Zeichenfolgen für ADO.NET

Veranschaulicht das Hinzufügen einer systemeigenen Unicodezeichenfolge (`wchar_t *`) mit einer Datenbank und das Marshallen einer <xref:System.String?displayProperty=fullName> aus einer Datenbank in eine systemeigene Unicodezeichenfolge.

### <a name="example"></a>Beispiel

In diesem Beispiel die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse ein systemeigenes C++ `class` (im Vergleich zu einem `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von nativem Code verwendet werden soll, und keine verwaltete Typen in systemeigenem Code können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie, die vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).

Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können nicht die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [Vorgehensweise: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).

Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code, gekennzeichnet durch die `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass Unicode-C++-Zeichenfolgen als Werte für die Datenbankspalte StringCol übergeben werden. Innerhalb der DatabaseClass diese Zeichenfolgen mit dem Marshalling-Funktionalität in verwaltete Zeichenfolgen gemarshallt werden die <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> zum Marshallen eine `wchar_t *` auf eine <xref:System.String>, und die Methode <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> zum Marshallen einer <xref:System.String> auf eine `wchar_t *`.

> [!NOTE]
>  Die Speichermenge von <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> muss aufgehoben werden, durch Aufrufen von entweder <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> oder `GlobalFree`.

```cpp
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

### <a name="compiling-the-code"></a>Kompilieren des Codes

- Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei, die mit dem Namen adonet_marshal_string_wide.cpp, und geben Sie die folgende Anweisung aus:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal_variant"></a> Marshallen eines VARIANT für ADO.NET

Veranschaulicht das Hinzufügen ein systemeigenen `VARIANT` mit einer Datenbank und das Marshallen einer <xref:System.Object?displayProperty=fullName> aus einer Datenbank in eine systemeigene `VARIANT`.

### <a name="example"></a>Beispiel

In diesem Beispiel die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse ein systemeigenes C++ `class` (im Vergleich zu einem `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von nativem Code verwendet werden soll, und keine verwaltete Typen in systemeigenem Code können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie, die vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).

Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können nicht die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [Vorgehensweise: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).

Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code, gekennzeichnet durch die `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass systemeigene `VARIANT` Typen werden als Werte für die Datenbankspalte ObjectCol übergeben wird. Innerhalb der DatabaseClass diese `VARIANT` Typen gemarshallt werden verwaltete Objekte, die mit dem Marshalling-Funktionalität der <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> zum Marshallen einer `VARIANT` auf ein <xref:System.Object>, und die Methode <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> zum Marshallen ein <xref:System.Object> auf eine `VARIANT`.

```cpp
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

### <a name="compiling-the-code"></a>Kompilieren des Codes

- Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei, die mit dem Namen adonet_marshal_variant.cpp, und geben Sie die folgende Anweisung aus:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal_safearray"></a> Marshallen eines SAFEARRAY für ADO.NET

Veranschaulicht das Hinzufügen ein systemeigenen `SAFEARRAY` mit einer Datenbank und das Marshallen eines verwalteten Arrays aus einer Datenbank in eine systemeigene `SAFEARRAY`.

### <a name="example"></a>Beispiel

In diesem Beispiel die Klasse DatabaseClass wird erstellt für die Interaktion mit einem ADO.NET <xref:System.Data.DataTable> Objekt. Beachten Sie, dass diese Klasse ein systemeigenes C++ `class` (im Vergleich zu einem `ref class` oder `value class`). Dies ist erforderlich, da diese Klasse von nativem Code verwendet werden soll, und keine verwaltete Typen in systemeigenem Code können. Diese Klasse wird kompiliert werden, um die CLR als Ziel ist die `#pragma managed` Richtlinie, die vor der Klassendeklaration. Weitere Informationen zu dieser Richtlinie, finden Sie unter [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md).

Beachten Sie den privaten Member der Klasse DatabaseClass: `gcroot<DataTable ^> table`. Da systemeigene Typen verwaltete Typen enthalten, können nicht die `gcroot` Schlüsselwort ist erforderlich. Weitere Informationen zu `gcroot`, finden Sie unter [Vorgehensweise: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md).

Der Rest des Codes in diesem Beispiel wird systemeigenem C++-Code, gekennzeichnet durch die `#pragma unmanaged` -Direktive vor `main`. In diesem Beispiel werden wir erstellen eine neue Instanz der DatabaseClass und Aufrufen ihrer Methoden zum Erstellen einer Tabelle und einige Zeilen in der Tabelle zu füllen. Beachten Sie, dass systemeigene `SAFEARRAY` Typen werden als Werte für die Datenbankspalte ArrayIntsCol übergeben wird. Innerhalb der DatabaseClass diese `SAFEARRAY` Typen gemarshallt werden verwaltete Objekte, die mit dem Marshalling-Funktionalität der <xref:System.Runtime.InteropServices?displayProperty=fullName> Namespace. Dabei wird die Methode <xref:System.Runtime.InteropServices.Marshal.Copy%2A> zum Marshallen einer `SAFEARRAY` in ein verwaltetes Array von ganzen Zahlen, und die Methode <xref:System.Runtime.InteropServices.Marshal.Copy%2A> zum Marshallen von eines verwalteten Arrays von ganzen Zahlen in einer `SAFEARRAY`.

```cpp
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

### <a name="compiling-the-code"></a>Kompilieren des Codes

- Um den Code über die Befehlszeile kompilieren, speichern Sie das Codebeispiel in einer Datei, die mit dem Namen adonet_marshal_safearray.cpp, und geben Sie die folgende Anweisung aus:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Informationen zu Sicherheitsaspekten bezüglich ADO.NET finden Sie unter [Sichern von ADO.NET-Anwendungen](/dotnet/framework/data/adonet/securing-ado-net-applications).

## <a name="related-sections"></a>Verwandte Abschnitte

|Abschnitt|Beschreibung|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|Bietet eine Übersicht über ADO.NET und einen Satz von Klassen, die Datenzugriffsdienste für .NET-Programmierer verfügbar machen.|

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Interoperabilität von nativem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[Interoperabilität](/dotnet/framework/interop/index)
