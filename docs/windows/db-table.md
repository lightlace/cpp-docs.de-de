---
title: Db_table | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e084a0f876d0b2598a5317e15057162c602474a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717118"
---
# <a name="dbtable"></a>db_table

Öffnet eine OLE DB-Tabelle.

## <a name="syntax"></a>Syntax

```cpp
[ db_table(
   db_table,
   name,
   source_name,
   hresult
) ]
```

#### <a name="parameters"></a>Parameter

*db_table*  
Eine Zeichenfolge, die den Namen einer Datenbanktabelle (z. B. "Produkte") angeben.

*name*  
(Optional) Der Name des Handles, die Sie verwenden, um die Arbeit mit der Tabelle. Sie müssen diesen Parameter angeben, wenn mehr als eine Zeile mit Ergebnissen zurückgegeben werden soll. **Db_table** generiert eine Variable mit dem angegebenen *Namen* , die verwendet werden kann, um das Rowset zu traversieren oder mehrere Aktionsabfragen auszuführen.

*source_name*  
(Optional) Die `CSession` Variable oder eine Instanz einer Klasse, die die `db_source` -Attribut angewendet, auf dem der Befehl ausgeführt wird. Informationen hierzu finden Sie unter [db_source](../windows/db-source.md).

*HRESULT*  
(Optional) Identifiziert die Variable, die das HRESULT des diesem Datenbankbefehl erhält. Wenn die Variable nicht existiert, wird sie automatisch durch das Attribut eingefügt.

## <a name="remarks"></a>Hinweise

**Db_table** erstellt eine [CTable](../data/oledb/ctable-class.md) -Objekt, das von einem OLE DB-Consumer verwendet wird, um eine Tabelle zu öffnen. Sie können dieses Attribut nur auf Klassenebene verwenden; Sie können keine sie Inline verwenden. Verwenden Sie `db_column` Tabellenspalten an Variablen gebunden verwenden `db_param` trennen (den Parametertyp, weshalb in festgelegt) von Parametern.

Wenn der Consumer Attributanbieter dieses Attribut auf eine Klasse angewendet wird, wird der Compiler die Klasse umbenennen \_ *Klassenname*Accessor, in denen *Klassenname* ist der Name, der Sie zugewiesen haben die Klasse und der Compiler erstellt auch eine Klasse namens *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.

## <a name="example"></a>Beispiel

Das folgende Beispiel öffnet die Products-Tabelle für die Verwendung durch `CProducts`.

```cpp
// db_table.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_table(L"dbo.Products") ]
class CProducts {
   [ db_column("1") ] LONG m_ProductID;
};
```

Ein Beispiel für dieses Attribut in einer Anwendung verwendet, finden Sie in den Beispielen [AtlAgent](https://github.com/Microsoft/VCSamples) und [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)  
