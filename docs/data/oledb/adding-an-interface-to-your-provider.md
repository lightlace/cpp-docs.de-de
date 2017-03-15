---
title: "Hinzuf&#252;gen einer Schnittstelle zum Anbieter | Microsoft Docs"
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
  - "OLE DB-Anbietervorlagen, Objektschnittstelle"
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Hinzuf&#252;gen einer Schnittstelle zum Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Entscheiden Sie, welchem Objekt die Schnittstelle hinzugefügt werden soll \(in der Regel einem vom OLE DB\-Anbieter\-Assistenten erstellten Datenquellen\-, Rowset\-, Befehls\- oder Sitzungsobjekt\).  Es ist möglich, dass das Objekt, dem die Schnittstelle hinzugefügt werden soll, derzeit nicht vom Anbieter unterstützt wird.  In diesem Fall führen Sie den ATL\-OLE DB\-Anbieter\-Assistenten aus, um das Objekt zu erstellen.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf das Projekt, und klicken Sie im Menü **Hinzufügen** auf **Klasse hinzufügen** und dann auf **ATL\-OLEDB\-Anbieter**.  Sie können den Schnittstellencode in einem separaten Verzeichnis speichern und die Dateien dann in das Anbieterprojekt kopieren.  
  
 Wenn Sie eine neue Klasse zur Unterstützung der Schnittstelle erstellt haben, muss das Objekt von dieser Klasse erben.  Sie können einem Rowsetobjekt beispielsweise die **IRowsetIndexImpl**\-Klasse hinzufügen:  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 Verwenden Sie das COM\_INTERFACE\_ENTRY\-Makro, um die Schnittstelle der **COM\_MAP** im Objekt hinzuzufügen.  Falls noch keine Zuordnung vorhanden ist, erstellen Sie diese.  Beispiel:  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Verketten Sie bei einem Rowsetobjekt die Zuordnung des übergeordneten Objekts, sodass das Objekt an die übergeordnete Klasse delegieren kann.  Fügen Sie in diesem Beispiel der Zuordnung das `COM_INTERFACE_ENTRY_CHAIN`\-Makro hinzu:  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)