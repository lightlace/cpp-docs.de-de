---
title: Verwenden von dynamischen Accessoren | Microsoft Docs
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 700a959742fafd4478659ff08821b043aff8bc14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111971"
---
# <a name="using-dynamic-accessors"></a>Verwenden von dynamischen Zugriffsmethoden

Dynamische Accessoren können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse des Datenbankschemas (zugrunde liegende Struktur) verfügen. Die OLE DB-Vorlagen-Bibliothek enthält mehrere Klassen, um Sie dabei unterstützt.

Die [-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) Beispiel wird gezeigt, wie Sie mithilfe der dynamischen Accessors-Klassen zum Abrufen von Spalteninformationen und Accessoren dynamisch erstellen.

## <a name="using-cdynamicaccessor"></a>Verwenden von CDynamicAccessor

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse des Datenbankschemas (die zugrunde liegende Struktur) verfügen. `CDynamicAccessor` Methoden erhalten Informationen wie z. B. Spaltennamen, Anzahl und den Datentyp in der Spalte. Sie verwenden diese Informationen in der Spalte um einen Accessor zur Laufzeit dynamisch zu erstellen. Die Informationen in der Spalte wird in einem Puffer gespeichert, die erstellt und verwaltet wird von dieser Klasse. Abrufen von Daten aus dem Puffer mithilfe der [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) Methode.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

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

## <a name="using-cdynamicstringaccessor"></a>Verwenden von CDynamicStringAccessor

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) funktioniert wie [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), außer in einem wichtigen Punkt. Während `CDynamicAccessor` fordert Daten im systemeigenen Format, die vom Anbieter gemeldeten `CDynamicStringAccessor` fordert an, dass der Anbieter alle Daten, die aus dem Datenspeicher als Zeichenfolgedaten zugegriffen abzurufen. Dies ist besonders für einfache Aufgaben, die keine Berechnung von Werten im Datenspeicher, z. B. anzeigen oder Drucken der Datenspeicher Inhalt erforderlich ist.

Verwendung `CDynamicStringAccessor` Methoden zum Abrufen von Spalteninformationen. Sie verwenden diese Informationen in der Spalte um einen Accessor zur Laufzeit dynamisch zu erstellen. Die Informationen in der Spalte befindet sich in einem Puffer, die von dieser Klasse erstellt und verwaltet. Abrufen von Daten aus dem Puffer mithilfe [CDynamicStringAccessor:: GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) oder speichern Sie sie in den Puffer mit [CDynamicStringAccessor:: SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

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

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) ähnelt [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), außer dass `CDynamicParameterAccessor` Plattforminformationen Parameter festzulegende durch Aufrufen der [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) -Schnittstelle. Der Anbieter muss `ICommandWithParameters` unterstützen, damit der Consumer diese Klasse verwenden kann.

Die Parameterinformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird. Rufen Sie die Parameterdaten aus dem Puffer mithilfe [CDynamicParameterAccessor:: GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) und [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Ein Beispiel veranschaulicht, wie diese Klasse verwenden, um eine gespeicherte SQL Server-Prozedur ausgeführt und die Ausgabeparameterwerte abrufen, finden Sie die [-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) Beispielcode in die [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) Repository auf GitHub.

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)  
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)  
[CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)  
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)  
[-Beispiel-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)  
