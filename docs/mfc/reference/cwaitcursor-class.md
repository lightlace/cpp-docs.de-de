---
title: "CWaitCursor Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWaitCursor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cursor, wait cursor"
  - "CWaitCursor class"
  - "wait cursors"
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CWaitCursor Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine einzeilige Möglichkeit, einen Wartecursor anzuzeigen, der normalerweise als Sanduhr angezeigt wird, während Sie einen längeren Vorgang ausführen.  
  
## Syntax  
  
```  
class CWaitCursor  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](../Topic/CWaitCursor::CWaitCursor.md)|Erstellt ein Objekt `CWaitCursor` und zeigt den Wartecursor an.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWaitCursor::Restore](../Topic/CWaitCursor::Restore.md)|Stellt den Wartecursor wiederhergestellt, nachdem er geändert wurde.|  
  
## Hinweise  
 `CWaitCursor` hat keine Basisklasse.  
  
 Gute Windows\-Programmierstile erfordern, dass Sie einen Wartecursor anzeigen, wenn Sie einen Vorgang ausführen, der recht lange dauert.  
  
 Um einen Wartecursor anzuzeigen, definieren Sie einfach eine `CWaitCursor`\-Variable vor dem Code der den längeren Vorgang ausführt.  Der Konstruktor des Objekts wird automatisch der Wartecursor angezeigt werden.  
  
 Wenn das Objekt den Gültigkeitsbereich verlässt \(am Ende des Blocks, in dem das `CWaitCursor`\-Objekt deklariert wurde\), dessen \- Destruktor den Cursor zum vorherigen Cursor fest.  Das bedeutet, dass das Objekt die erforderliche Bereinigung automatisch aus.  
  
> [!NOTE]
>  Aufgrund, wie ihre Konstruktoren und Destruktoren arbeiten, werden `CWaitCursor`\-Objekte immer als lokale Variablen deklariert \- sie werden nie als globale Variablen deklariert, noch sind sie mit **new** zugeordnet haben.  
  
 Wenn Sie einen Vorgang ausführen, der möglicherweise den Cursor wurde, wie das Anzeigen eines Meldungsfelds oder Dialogfeld geändert, rufen Sie die [Wiederherstellung](../Topic/CWaitCursor::Restore.md)\-Memberfunktion auf, um den Wartecursor wiederherzustellen.  Es ist eine, **Wiederherstellen** aufzurufen, selbst wenn ein Wartecursor gerade angezeigt wird.  
  
 Eine andere Möglichkeit, einen Wartecursor anzuzeigen, die Kombination von [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md), von [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md) und kann von [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md) zu verwenden.  `CWaitCursor` ist jedoch einfacher zu verwenden, da Sie nicht erforderlich ist, um den Cursor zum vorherigen Cursor festzulegen, wenn Sie mit dem längeren Vorgang durchgeführt werden.  
  
> [!NOTE]
>  MFC legt fest und stellt den Cursor mit virtuellen Funktion [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md) wieder her.  Sie können diese Funktion überschreiben, um ein benutzerdefiniertes Verhalten bereitzustellen.  
  
## Vererbungshierarchie  
 `CWaitCursor`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Beispiel  
 [!CODE [NVC_MFCWindowing#62](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCWindowing#62)]  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)   
 [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)   
 [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)   
 [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)   
 [Wie behebe ich: Ändern Sie den Mauszeiger in einer Microsoft Foundation Class\-Anwendung?](http://go.microsoft.com/fwlink/?LinkID=128044)