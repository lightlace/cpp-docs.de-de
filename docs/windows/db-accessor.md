---
title: Db_accessor | Microsoft Docs
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
ms.openlocfilehash: b81e55500a8ff44c887bed592c9472c5a8d3ea1d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="dbaccessor"></a>db_accessor
Gruppen **Db_column** Attribute, die Teilnahme an `IAccessor`-basierten Bindung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *num*  
 Gibt die Anzahl der Accessor (einen nullbasierten ganzzahligen Index). Sie müssen die Zugriffsmethode Zahlen in aufsteigender Reihenfolge anhand von ganzen Zahlen oder benutzerdefinierte Werte angeben.  
  
 *auto*  
 Ein boolescher Wert, der angibt, ob der Accessor automatisch abgerufen wird (**"true"**) oder nicht abgerufen (**"false"**).  
  
## <a name="remarks"></a>Hinweise  
 **Db_accessor** definiert den zugrunde liegenden OLE DB-Accessor für nachfolgende **Db_column** und **Db_param** Attribute innerhalb der gleichen Klasse oder Funktion. **Db_accessor** kann auf Memberebene verwendet werden und wird verwendet, zur Gruppe **Db_column** Attribute, die Bestandteil der OLE DB- `IAccessor`-basierten Bindung. Es dient in Verbindung mit der **Db_table** oder **Db_command** Attribute. Dieses Attribut aufrufen gleicht dem Aufruf der [BEGIN_ACCESSOR](../data/oledb/begin-accessor.md) und [END_ACCESSOR](../data/oledb/end-accessor.md) Makros.  
  
 **Db_accessor** ein Rowset generiert und bindet sie an der entsprechenden Accessor Zuordnungen. Wenn Sie nicht aufrufen **Db_accessor**Accessor 0 wird automatisch generiert und alle spaltenbindungen werden dieser Accessorblock zugeordnet werden.  
  
 **Db_accessor** Gruppen Datenbank in eine oder mehrere Accessoren spaltenbindungen. Eine Erläuterung der Szenarien, in denen Sie mehrere Accessoren für Ereigniseigenschaften verwenden müssen, finden Sie unter [Verwenden mehrerer Accessoren für ein Rowset](../data/oledb/using-multiple-accessors-on-a-rowset.md). Siehe auch "Benutzer Datensatz Unterstützung für mehrere Accessoren" in [Benutzerdatensätze](../data/oledb/user-records.md).  
  
 Wenn vom Consumer-Attribut-Anbieter dieses Attribut auf eine Klasse angewendet werden, wird der Compiler die Klasse umbenennen \_ *Klassenname*-Accessor, in dem *Klassenname* der eingegebene Name ist der Klasse und der Compiler erstellt auch eine Klasse mit dem Namen *Klassenname*, die sich daraus ableitet \_ *Klassenname*Accessor.  In dieser Klassenansicht werden beide Klassen angezeigt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird **Db_accessor** zum Gruppieren der Spalten in der Orders-Tabelle aus der Northwind-Datenbank in beiden Accessoren. 0-Accessor ist eine automatische Zugriffsmethode und 1 der Accessor ist kein.  
  
```  
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
