---
title: Db_source (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: 884cab78d64c20bef00958f0cc0319281fd69921
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148106"
---
# <a name="dbsource"></a>db_source

Erstellt eine Verbindung mit einer Datenquelle.

## <a name="syntax"></a>Syntax

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>Parameter

*db_source*<br/>
Die Verbindungszeichenfolge für die Verbindung mit der Datenquelle verwendet wird. Das Format der Verbindungszeichenfolge finden Sie unter [Verbindungszeichenfolgen und Datenverknüpfungen](/previous-versions/windows/desktop/ms718376(v=vs.85)) in der Microsoft Data Access Components (MDAC) SDK.

*name*<br/>
(Optional) Bei Verwendung von **Db_source** für eine Klasse, *Namen* ist eine Instanz von einem Datenquellenobjekt an, die die **Db_source** angewendet werden (siehe Beispiel 1). Bei Verwendung von **Db_source** Inline in der Implementierung einer Methode *Namen* ist eine Variable (lokal in der Methode), die für den Datenzugriff verwendet werden kann (siehe Beispiel 2). Übergeben Sie das *Namen* auf die *Source_name* Parameter `db_command` , einen Befehl die Datenquelle zugeordnet werden soll.

*hresult*<br/>
(Optional) Identifiziert die Variable, die das HRESULT des diesem Datenbankbefehl erhält. Wenn die Variable nicht existiert, wird sie automatisch durch das Attribut eingefügt.

## <a name="remarks"></a>Hinweise

**Db_source** erstellt eine [CDataSource](../../data/oledb/cdatasource-class.md) und [CSession](../../data/oledb/csession-class.md) -Objekt, das zusammen eine Verbindung mit einer OLE DB-Consumer-Datenquelle darstellen.

Bei Verwendung von **Db_source** für eine Klasse, die `CSession` Objekt wird ein Member der Klasse.

Bei Verwendung von **Db_source** der eingefügte Code wird in einer Methode innerhalb des Gültigkeitsbereichs Methode ausgeführt werden und die `CSession` Objekt wird als lokale Variable erstellt.

**Db_source** fügt die Eigenschaften der Datenquelle auf eine Klasse oder innerhalb einer Methode hinzu. Es dient in Verbindung mit `db_command` (nimmt die *Db_source* *Namen* Parameter als die *Source_name* Parameter).

Wenn der Consumer Attributanbieter dieses Attribut auf eine Klasse angewendet wird, wird der Compiler die Klasse umbenennen \_ *Klassenname*Accessor, in denen *Klassenname* ist der Name, der Sie zugewiesen haben die Klasse und der Compiler erstellt auch eine Klasse namens *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.

Ein Beispiel für dieses Attribut in einer Anwendung verwendet, finden Sie in den Beispielen [AtlAgent](https://github.com/Microsoft/VCSamples) und [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="example"></a>Beispiel

In diesem Beispiel ruft **Db_source** für eine Klasse zum Erstellen einer Verbindung mit der Datenquelle `ds` mit der Northwind-Datenbank. `ds` ist ein Handle für die Datenquelle, die intern auf verwendet werden, kann die `CMyCommand` Klasse.

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")
]
class CMyCommand {};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, Member, Methode, lokal|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumerattribute](ole-db-consumer-attributes.md)
