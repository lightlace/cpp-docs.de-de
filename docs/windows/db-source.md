---
title: Db_source | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18c4a4af3f8df4e3af5f6aae8f6643db553c7373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dbsource"></a>db_source
Erstellt eine Verbindung mit einer Datenquelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *db_source*  
 Die Verbindungszeichenfolge für die Verbindung mit der Datenquelle verwendet wird. Das Format der Verbindungszeichenfolge finden Sie unter [Verbindungszeichenfolgen und Datenverknüpfungen](https://msdn.microsoft.com/en-us/library/ms718376.aspx) in Microsoft Data Access Components (MDAC) SDK.  
  
 *name* (optional)  
 Bei Verwendung von `db_source` für eine Klasse *Namen* ist eine Instanz des ein Datenquellenobjekt, das verfügt die `db_source` angewendet werden (siehe Beispiel 1). Bei Verwendung von `db_source` Inline in der Implementierung einer Methode *Namen* ist eine Variable (lokal an die Methode), die für den Datenzugriff verwendet werden kann (siehe Beispiel 2). Übergeben Sie das *Namen* auf die `source_name` Parameter **Db_command** eines Befehls die Datenquelle zugeordnet werden soll.  
  
 `hresult` (optional)  
 Identifiziert die Variable, die `HRESULT` von diesem Datenbankbefehl erhält. Wenn die Variable nicht existiert, wird sie automatisch durch das Attribut eingefügt.  
  
## <a name="remarks"></a>Hinweise  
 `db_source`erstellt eine [CDataSource](../data/oledb/cdatasource-class.md) und ein [CSession](../data/oledb/csession-class.md) -Objekt, das zusammen eine Verbindung mit einer OLE DB-Consumer-Datenquelle darstellen.  
  
 Bei Verwendung von `db_source` für eine Klasse, die `CSession` Objekt wird ein Member der Klasse.  
  
 Bei Verwendung von `db_source` in einer Methode, wird der injizierten Code innerhalb des Gültigkeitsbereichs Methode ausgeführt werden und die `CSession` Objekt wird als lokale Variable erstellt.  
  
 `db_source`Fügt Datenquelleneigenschaften hinzu, um eine Klasse oder innerhalb einer Methode. Es dient in Verbindung mit **Db_command** (nimmt die `db_source` *Namen* Parameter als seine `source_name` Parameter).  
  
 Wenn vom Consumer-Attribut-Anbieter dieses Attribut auf eine Klasse angewendet werden, wird der Compiler die Klasse umbenennen \_ *Klassenname*-Accessor, in dem *Klassenname* der eingegebene Name ist der Klasse und der Compiler erstellt auch eine Klasse mit dem Namen *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.  
  
 Ein Beispiel für dieses Attribut in einer Anwendung verwendet, finden Sie in den Beispielen [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) und [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ruft `db_source` für eine Klasse zum Erstellen einer Verbindung mit der Datenquelle `ds` mit der Northwind-Datenbank. `ds`ist ein Handle für die Datenquelle, die intern auf verwendet werden kann die `CMyCommand` Klasse.  
  
```  
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
|**Betrifft**|**Klasse**, `struct`, Member, Methode, lokal|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)   
