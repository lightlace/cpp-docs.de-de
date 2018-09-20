---
title: Db_accessor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_accessor
dev_langs:
- C++
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61c20647d96a66cf4b50e6f0b031cc04353553e5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410649"
---
# <a name="dbaccessor"></a>db_accessor

Gruppen `db_column` Attribute, die Teilnahme an `IAccessor`-basierten Bindung.

## <a name="syntax"></a>Syntax

```cpp
[ db_accessor(
   num,
   auto
) ]
```

#### <a name="parameters"></a>Parameter

*num*<br/>
Gibt die Anzahl der Accessor (eine nullbasierte ganze Zahl Index). Sie müssen die Accessor-Zahlen in aufsteigender Reihenfolge anhand von ganzen Zahlen oder definierten Werte angeben.

*auto*<br/>
Ein boolescher Wert, der angibt, ob der Accessor automatisch abgerufen (TRUE) oder nicht (FALSE) abgerufen.

## <a name="remarks"></a>Hinweise

**Db_accessor** definiert den zugrunde liegenden OLE DB-Accessor für nachfolgende `db_column` und `db_param` Attribute innerhalb der gleichen Klasse oder Funktion. **Db_accessor** kann verwendet werden, auf Elementebene und dient zur Gruppe `db_column` Attribute, die Teilnahme an OLE DB `IAccessor`-basierten Bindung. Es dient in Verbindung mit der `db_table` oder `db_command` Attribute. Dieses Attribut aufrufen ist vergleichbar mit einem Aufruf der [BEGIN_ACCESSOR](../data/oledb/begin-accessor.md) und [END_ACCESSOR](../data/oledb/end-accessor.md) Makros.

**Db_accessor** ein Rowset generiert, und bindet sie an der entsprechenden Accessor-Zuordnungen. Wenn Sie nicht aufrufen **Db_accessor**Accessor 0 ist, wird automatisch generiert werden und alle spaltenbindungen dieser Accessorblock zugeordnet.

**Db_accessor** Gruppen Datenbank spaltenbindungen in eine oder mehrere Accessoren. Eine Erläuterung der Szenarien, in dem Sie mehrere Accessoren für Ereigniseigenschaften verwenden möchten, finden Sie unter [Verwenden mehrerer Zugriffsmethoden für ein Rowset](../data/oledb/using-multiple-accessors-on-a-rowset.md). Außerdem finden Sie unter "Benutzer Datensatz Unterstützung für mehrere Accessoren" in [Benutzerdatensätze](../data/oledb/user-records.md).

Wenn der Consumer Attributanbieter dieses Attribut auf eine Klasse angewendet wird, wird der Compiler die Klasse umbenennen \_ *Klassenname*Accessor, in denen *Klassenname* ist der Name, der Sie zugewiesen haben die Klasse und der Compiler erstellt auch eine Klasse namens *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird **Db_accessor** zum Gruppieren der Spalten in der Orders-Tabelle aus der Northwind-Datenbank in beiden Accessoren. 0-Accessor ist eine automatische Accessor, und 1 der Accessor ist kein.

```cpp
// cpp_attr_ref_db_accessor.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>

[ db_command(L"SELECT LastName, FirstName FROM Orders") ]
class CEmployees {
public:
   [ db_accessor(0, TRUE) ];
   [ db_column("1") ] LONG m_OrderID;
   [ db_column("2") ] TCHAR m_CustomerID[6];
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;

   [ db_accessor(1, FALSE) ];
   [ db_column("8") ] CURRENCY m_Freight;
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Attributblöcke|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)  