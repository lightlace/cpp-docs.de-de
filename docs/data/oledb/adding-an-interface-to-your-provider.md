---
title: Hinzufügen einer Schnittstelle zum Anbieter | Microsoft Docs
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
ms.openlocfilehash: 3d6bc5d1b6c47d2ffa26bffa98d47b930d6ed193
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-an-interface-to-your-provider"></a>Hinzufügen einer Schnittstelle zum Anbieter
Bestimmen Sie, welches Objekt, das die Schnittstelle für (in der Regel Data Source, Rowsets, Befehls- oder Sitzung erstellten Objekte vom OLE DB-Anbieter-Assistenten) hinzufügen möchten. Es ist möglich, dass das Objekt, dem Sie die Schnittstelle zum hinzufügen müssen, die Ihr Anbieter derzeit nicht unterstützt. In diesem Fall führen Sie den ATL OLE DB-Anbieter-Assistenten aus, um das Objekt zu erstellen. Mit der rechten Maustaste des Projekts in der Klassenansicht, klicken Sie auf **Klasse hinzufügen** aus der **hinzufügen** Menü, und klicken Sie dann auf **ATL-OLE DB-Anbieter**. Möglicherweise möchten den Code für die Benutzeroberfläche in einem separaten Verzeichnis abgelegt, und kopieren Sie die Dateien zu Ihrem Anbieterprojekt.  
  
 Wenn Sie eine neue Klasse zur Unterstützung der-Schnittstelle erstellt haben, stellen Sie das Objekt, das von dieser Klasse erben. Beispielsweise können Sie die Klasse hinzufügen **IRowsetIndexImpl** einem Rowsetobjekt:  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
 Fügen Sie die Schnittstelle zum **COM_MAP** in das Objekt mit dem COM_INTERFACE_ENTRY-Makro. Wenn keine Zuordnung vorhanden ist, erstellen. Zum Beispiel:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Für das Rowsetobjekt Kette die Zuordnung des übergeordneten Objekt, sodass das Objekt an die übergeordnete Klasse delegieren kann. Fügen Sie in diesem Beispiel der Karte-Makro hinzu:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)