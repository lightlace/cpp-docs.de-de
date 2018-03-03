---
title: Db_table | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37dd6fd80a0d18f1b9d93f5299fca797238a509f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Eine Zeichenfolge, die den Namen einer Datenbanktabelle (z. B. "Products") angeben.  
  
 *name* (optional)  
 Der Name des Handles, die Sie zum Arbeiten mit der Tabelle verwenden. Sie müssen diesen Parameter angeben, wenn mehr als eine Zeile von Ergebnissen zurückgegeben werden soll. **Db_table** generiert eine Variable mit dem angegebenen *Namen* , die verwendet werden kann, durchlaufen das Rowset oder mehrere Aktionsabfragen ausführen.  
  
 *source_name* (optional)  
 Die Variable `CSession` oder die Instanz einer Klasse, auf die das `db_source` -Attribut angewendet wird, auf Grundlage dessen der Befehl ausgeführt wird. Informationen hierzu finden Sie unter [db_source](../windows/db-source.md).  
  
 `hresult` (optional)  
 Identifiziert die Variable, die `HRESULT` von diesem Datenbankbefehl erhält. Wenn die Variable nicht existiert, wird sie automatisch durch das Attribut eingefügt.  
  
## <a name="remarks"></a>Hinweise  
 **Db_table** erstellt eine [CTable](../data/oledb/ctable-class.md) -Objekt, das von einer OLE DB-Consumer verwendet wird, um eine Tabelle zu öffnen. Sie können dieses Attribut nur auf Klassenebene verwenden; Sie können nicht Inline verwenden. Verwenden Sie **Db_column** zum Binden von Spalten in der Tabelle an Variablen; verwenden Sie **Db_param** zur Begrenzung von (Festlegen der Parametertyp und daher auf) von Parametern.  
  
 Wenn vom Consumer-Attribut-Anbieter dieses Attribut auf eine Klasse angewendet werden, wird der Compiler die Klasse umbenennen \_ *Klassenname*-Accessor, in dem *Klassenname* der eingegebene Name ist der Klasse und der Compiler erstellt auch eine Klasse mit dem Namen *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Products-Tabelle für die Verwendung durch `CProducts`.  
  
```  
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
  
 Ein Beispiel für dieses Attribut in einer Anwendung verwendet, finden Sie in den Beispielen [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) und [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumerattribute](../windows/ole-db-consumer-attributes.md)   
