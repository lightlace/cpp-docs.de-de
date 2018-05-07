---
title: IRowsetChangeImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 11435cd1372147efb14aed78448d889fd60dc5a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl-Klasse
Die OLE DB-Vorlagen-Implementierung von der [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) Schnittstelle in der OLE DB-Spezifikation.  
  
## <a name="syntax"></a>Syntax

```cpp
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse `IRowsetChangeImpl`.  
  
 `Storage`  
 Der Benutzerdatensatz enthält.  
  
 `BaseInterface`  
 Die Basisklasse für die Schnittstelle, wie z. B. `IRowsetChange`.  
  
 `RowClass`  
 Die speichereinheit für das Zeilenhandle.  
  
 `MapClass`  
 Für alle Zeilenhandles, die vom Anbieter Storage-Einheit.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Schnittstellenmethoden (mit IRowsetChange verwendet)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|Löscht Zeilen aus dem Rowset.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Fügt eine Zeile in das Rowset an.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|Legt Datenwerte in einer oder mehreren Spalten fest.|  
  
### <a name="implementation-method-callback"></a>Die Implementierungsmethode (Callback)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Außer Kraft gesetzt, vom Anbieter, um Daten an seinen Speicher zu übertragen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist verantwortlich für sofortige Schreibvorgänge in einem Datenspeicher. "Sofortige" bedeutet, dass wenn der Endbenutzer (der Person, die mit der Consumer) Änderungen vornimmt, diese Änderungen sofort an den Daten übertragen werden speichern (und können nicht rückgängig gemacht werden).  
  
 `IRowsetChangeImpl` implementiert die OLE DB- `IRowsetChange` -Schnittstelle, die Aktualisieren der Werte der Spalten in vorhandenen Zeilen löschen von Zeilen, und neue Zeilen einfügen kann.  
  
 Die Implementierung der OLE DB-Vorlagen unterstützt alle Basismethoden (`SetData`, `InsertRow`, und `DeleteRows`).  
  
> [!IMPORTANT]
>  Es wird dringend empfohlen, dass Sie die folgende Dokumentation, bevor Sie versuchen, einen Anbieter implementieren lesen:  
  
-   [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Kapitel 6 der *OLE DB-Programmierreferenz*  
  
-   Siehe auch wie die `RUpdateRowset` Klasse wird verwendet, in dem UpdatePV-Beispiel  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)