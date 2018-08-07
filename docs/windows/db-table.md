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
ms.openlocfilehash: 91eea8bd751e4e8e843fb2d052f2b4a71f9bdc38
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570336"
---
# <a name="dbtable"></a>db_table
Öffnet eine OLE DB-Tabelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
 *name* (optional)  
 Der Name des Handles, die Sie verwenden, um die Arbeit mit der Tabelle. Sie müssen diesen Parameter angeben, wenn mehr als eine Zeile mit Ergebnissen zurückgegeben werden soll. **Db_table** generiert eine Variable mit dem angegebenen *Namen* , die verwendet werden kann, um das Rowset zu traversieren oder mehrere Aktionsabfragen auszuführen.  
  
 *source_name* (optional)  
 Die Variable `CSession` oder die Instanz einer Klasse, auf die das `db_source` -Attribut angewendet wird, auf Grundlage dessen der Befehl ausgeführt wird. Informationen hierzu finden Sie unter [db_source](../windows/db-source.md).  
  
 *HRESULT* (optional)  
 Identifiziert die Variable, die das HRESULT des diesem Datenbankbefehl erhält. Wenn die Variable nicht existiert, wird sie automatisch durch das Attribut eingefügt.  
  
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
  
 Ein Beispiel für dieses Attribut in einer Anwendung verwendet, finden Sie in den Beispielen [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409) und [MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
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