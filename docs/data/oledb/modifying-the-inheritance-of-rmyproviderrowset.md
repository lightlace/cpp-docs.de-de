---
title: "Ändern der Vererbung von \"RMyProviderRowset\" | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e8ecfe35d61762b8beaa217eaacc4202a588debb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>Ändern der Vererbung von "RMyProviderRowset"
Hinzufügen der `IRowsetLocate` Schnittstelle mit dem einfachen schreibgeschützten Anbieters-Beispiel, ändern Sie die Vererbung von **"RMyProviderRowset"**. Zu Beginn **"RMyProviderRowset"** erbt von `CRowsetImpl`. Müssen Sie es zu vererben ändern **CRowsetBaseImpl**.  
  
 Zu diesem Zweck erstellen Sie eine neue Klasse `CMyRowsetImpl`, in MyProviderRS.h:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate > >  
{  
...  
};  
```  
  
 Bearbeiten Sie nun die COM-schnittstellenzuordnung in MyProviderRS.h wie folgt sein:  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Dies erstellt eine COM-Schnittstelle, die mitteilt, `CMyRowsetImpl` Aufrufen **QueryInterface** für beide die `IRowset` und `IRowsetLocate` Schnittstellen. Klassen zum Abrufen aller die Implementierung für andere Rowset die zuordnungslinks der `CMyRowsetImpl` Klasse zurück, an die **CRowsetBaseImpl** Klasse durch den OLE DB-Vorlagen definiert; die-Makro, wodurch angewiesen wird verwendet OLE DB-Vorlagen, überprüfen Sie die COM-Zuordnung in **CRowsetBaseImpl** als Antwort auf eine `QueryInterface` aufrufen.  
  
 Verknüpfen Sie schließlich `RAgentRowset` auf `CMyRowsetBaseImpl` durch Ändern von `RAgentRowset` zu vererben `CMyRowsetImpl`wie folgt:  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset`Nun können Sie die `IRowsetLocate` Schnittstelle profitieren von der Rest der Implementierung für die Rowsetklasse.  
  
 Nachdem dies geschehen ist, können Sie [dynamisch bestimmen an den Consumer zurückgegebene Spalten](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)