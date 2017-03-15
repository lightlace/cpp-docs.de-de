---
title: "&#196;ndern der Vererbung von &quot;RMyProviderRowset&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vererbung [C++]"
  - "RMyProviderRowset"
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# &#196;ndern der Vererbung von &quot;RMyProviderRowset&quot;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um dem einfachen schreibgeschützten Anbieter die `IRowsetLocate`\-Schnittstelle hinzuzufügen, ändern Sie die Vererbung von **RMyProviderRowset**.  In der ursprünglichen Einstellung erbt **RMyProviderRowset** von `CRowsetImpl`.  Sie müssen diese Einstellung ändern, um die Vererbung von **CRowsetBaseImpl** zu ermöglichen.  
  
 Sie erstellen dazu in **MyProviderRS.h** die neue `CMyRowsetImpl`\-Klasse:  
  
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
  
 Anschließend ändern Sie die COM\-Schnittstellenzuordnung in **MyProviderRS.h** wie folgt:  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Auf diese Weise wird eine COM\-Schnittstellenzuordnung erstellt, mit deren Hilfe `CMyRowsetImpl` angewiesen wird, **QueryInterface** sowohl für die `IRowset`\-Schnittstelle als auch für die `IRowsetLocate`\-Schnittstelle aufzurufen.  Um die anderen Rowsetklassen vollständig zu implementieren, wird die `CMyRowsetImpl`\-Klasse durch die Zuordnung wieder mit der in den OLE DB\-Vorlagen definierten **CRowsetBaseImpl**\-Klasse verknüpft. Die Zuordnung verwendet das `-Makro, das Informationen für die OLE DB-Vorlagen enthält, durch die als Reaktion auf einen QueryInterface`\-Aufruf die COM\-Zuordnung in **CRowsetBaseImpl** durchsucht wird.  
  
 Zuletzt verknüpfen Sie `RAgentRowset` mit `CMyRowsetBaseImpl`, indem Sie `RAgentRowset`, wie im Folgenden dargestellt, ändern, sodass von `CMyRowsetImpl` geerbt wird:  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 Nun kann `RAgentRowset` die `IRowsetLocate`\-Schnittstelle verwenden und gleichzeitig die Vorteile der übrigen Implementierung für die Rowsetklasse nutzen.  
  
 Nachdem dieser Schritt abgeschlossen ist, können Sie [dynamisch festlegen, welche Spalten an den Consumer zurückgegeben werden](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## Siehe auch  
 [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)