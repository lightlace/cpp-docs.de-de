---
title: Verwenden von dynamischen Zugriffsmethoden
ms.date: 10/18/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
ms.openlocfilehash: 4539247894c3980464e744c76cea450324372382
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649721"
---
# <a name="using-dynamic-accessors"></a>Verwenden von dynamischen Zugriffsmethoden

Dynamische Zugriffsmethoden können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse über das Datenbankschema (zugrunde liegende Struktur) verfügen. Die OLE DB-Vorlagen-Bibliothek enthält mehrere Klassen, die Ihnen helfen.

Die [-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) Beispiel zeigt, wie Sie mithilfe die dynamischen Accessorklassen Spalteninformationen und Accessoren dynamisch erstellen.

## <a name="using-cdynamicaccessor"></a>Verwenden von CDynamicAccessor

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse über das Datenbankschema (die zugrunde liegende Struktur) verfügen. `CDynamicAccessor` Methoden rufen Informationen wie z. B. Spaltennamen, Anzahl und Datentyp. Sie können diese Spalteninformationen verwenden, um einen Accessor dynamisch zur Laufzeit zu erstellen. Die Spalteninformationen wird in einem Puffer gespeichert, die erstellt und verwaltet wird, die von dieser Klasse. Abrufen von Daten aus dem Puffer mithilfe der ["GetValue"](../../data/oledb/cdynamicaccessor-getvalue.md) Methode.

## <a name="example"></a>Beispiel

```cpp
// Using_Dynamic_Accessors.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );

    CDataSource ds;
    CSession ss;

    CTable<CDynamicAccessor> rs;

    // The following is an example initialization string:
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"
      L"Integrated Security=SSPI;Persist Security Info=False;"
      L"Initial Catalog=Loginname;Data Source=your_data_source;"
      L"Use Procedure for Prepare=1;Auto Translate=True;"
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"
      L"Use Encryption for Data=False;"
      L"Tag with column collation when possible=False");

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            DBTYPE type;
            rs.GetColumnType(i, &type );
            printf_s( "Column %d [%S] is of type %d\n",
                      i, rs.GetColumnName(i ), type );

            switch(type )
            {
                case DBTYPE_WSTR:
                    printf_s( "value is %S\n",
                              (WCHAR*)rs.GetValue(i ) );
                break;
                case DBTYPE_STR:
                    printf_s( "value is %s\n",
                              (CHAR*)rs.GetValue(i ) );
                default:
                    printf_s( "value is %d\n",
                              *(long*)rs.GetValue(i ) );
            }
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

    return 0;
}
```

## <a name="using-cdynamicstringaccessor"></a>CDynamicStringAccessor verwenden

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) funktioniert wie [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), mit Ausnahme der in einem wichtigen Punkt. Während `CDynamicAccessor` fordert Daten in das systemeigene Format, die vom Anbieter gemeldeten `CDynamicStringAccessor` angefordert wird, dass der Anbieter alle Daten aus dem Datenspeicher als Zeichenfolgedaten abruft. Der Prozess ist besonders nützlich für einfache Aufgaben, die Berechnung der Werte in den Datenspeicher, z. B. anzeigen oder drucken den Data Store Inhalt nicht benötigen.

Verwendung `CDynamicStringAccessor` Methoden zum Abrufen der Spalteninformationen. Sie können diese Spalteninformationen verwenden, um einen Accessor dynamisch zur Laufzeit zu erstellen. Die Spalteninformationen befindet sich in einem Puffer, die von dieser Klasse erstellt und verwaltet. Abrufen von Daten aus dem Puffer mithilfe [CDynamicStringAccessor:: GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) oder das Speichern in den Puffer mit [CDynamicStringAccessor:: SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).

## <a name="example"></a>Beispiel

```cpp
// Using_Dynamic_Accessors_b.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );
    if (hr != S_OK)
    {
        exit (-1);
    }

    CDataSource ds;
    CSession ss;

    CTable<CDynamicStringAccessor> rs;

    // The following is an example initialization string:
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"
      L"Integrated Security=SSPI;Persist Security Info=False;"
      L"Initial Catalog=Loginname;Data Source=your_data_source;"
      L"Use Procedure for Prepare=1;Auto Translate=True;"
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"
      L"Use Encryption for Data=False;"
      L"Tag with column collation when possible=False");

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            printf_s( "column %d value is %s\n",
                      i, rs.GetString(i ) );
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

   return 0;
}
```

## <a name="using-cdynamicparameteraccessor"></a>Verwenden von CDynamicParameterAccessor

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) ist vergleichbar mit [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), außer dass `CDynamicParameterAccessor` Ruft Parameterinformationen festzulegende durch Aufrufen der [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) Schnittstelle. Der Anbieter muss `ICommandWithParameters` unterstützen, damit der Consumer diese Klasse verwenden kann.

Die Parameterinformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird. Rufen Sie Parameterdaten aus dem Puffer mit [CDynamicParameterAccessor:: GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) und [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Ein Beispiel veranschaulicht, wie diese Klasse zum Ausführen einer gespeicherten SQL Server-Prozedur und die Ausgabeparameterwerte zu erhalten, finden Sie die [-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) Beispielcode in die [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) GitHub-Repository.

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)<br/>
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[-Beispiel-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)
