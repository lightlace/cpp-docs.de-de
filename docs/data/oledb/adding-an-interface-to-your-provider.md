---
title: Hinzufügen einer Schnittstelle zum Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f50459550c91f07c12f6f18b3fbbaa5622ab7408
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032392"
---
# <a name="adding-an-interface-to-your-provider"></a>Hinzufügen einer Schnittstelle zum Anbieter

Bestimmen Sie, welches Objekt, das die Schnittstelle (in der Regel Data Source, Rowset, Befehl oder Sitzung vom OLE DB-Anbieter-Assistenten erstellt) hinzugefügt werden soll. Es ist möglich, dass das Objekt, dem Sie die Schnittstelle zum hinzufügen müssen einer, der Ihrem Anbieter derzeit nicht unterstützt. In diesem Fall führen Sie die ATL-OLE DB-Anbieter-Assistenten aus, um das Objekt zu erstellen. Mit der rechten Maustaste in des Projekts in der Klassenansicht, klicken Sie auf **Klasse hinzufügen** aus der **hinzufügen** , und klicken Sie dann auf **ATL-OLE DB-Anbieter**. Sie möchten den Code für die Benutzeroberfläche in einem separaten Verzeichnis abgelegt und kopieren Sie die Dateien zu Ihrem Anbieterprojekt.  
  
Wenn Sie eine neue Klasse zum unterstützen der Schnittstelle erstellt haben, stellen Sie das Objekt, das von dieser Klasse erben. Beispielsweise können Sie die Klasse hinzufügen **IRowsetIndexImpl** in ein Rowsetobjekt:  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
Fügen Sie die Schnittstelle für **COM_MAP** in das Objekt, das mit dem COM_INTERFACE_ENTRY-Makro. Wenn keine Zuordnung vorhanden ist, erstellen. Zum Beispiel:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
Für das Rowsetobjekt die Kette der Zuordnung des übergeordneten Objekts, sodass das Objekt in der übergeordneten Klasse delegieren kann. Fügen Sie in diesem Beispiel der Zuordnung-Makro hinzu:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>Siehe auch  

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)