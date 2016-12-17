---
title: "CCreateContext Structure"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CCreateContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCreateContext structure"
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CCreateContext Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Framework verwendet die `CCreateContext`\-Struktur, wenn die Rahmenfenster und Ansichten erstellt, die einem Dokument zugeordnet werden.  
  
## Syntax  
  
```  
struct CCreateContext  
```  
  
## Hinweise  
 `CCreateContext` ist eine Struktur und hat keine Basisklasse.  
  
 Wenn Sie ein Fenster erstellen, stellen die Werte in dieser Struktur die Informationen, die verwendet werden, um die Komponenten eines Dokuments an die Ansicht der Daten herzustellen.  Sie müssen `CCreateContext` nur verwenden, wenn Sie überschreiben Teile des Erstellungsprozesses sind.  
  
 Eine `CCreateContext`\-Struktur enthält Zeiger auf das Dokument, an das Rahmenfenster, zur Ansicht und die Normal\-Vorlage.  Sie enthält auch einen Zeiger auf `CRuntimeClass`, der den Typ der Ansicht identifiziert, um zu erstellen.  Die Ablaufklasseninformationen und der Zeiger des aktuellen Dokuments werden verwendet, um eine neue Ansicht dynamisch zu erstellen.  In der folgenden Tabelle schlägt vor, wie und wann jeder `CCreateContext`\-Member werden könnte:  
  
|Member|Typ|Für deren ist|  
|------------|---------|-------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` der neuen Ansicht zu erstellen.|  
|`m_pCurrentDoc`|`CDocument*`|Das vorhandene mit der neuen Ansicht zugeordnet werden, Dokument.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Die Normal\-Vorlage zugeordnet mit der Erstellung eines neuen MDI\-Rahmenfensters.|  
|`m_pLastView`|`CView*`|Die ursprüngliche Ansicht, auf der weitere Ansichten modelliert werden, wie in die Erstellung von Splitterfensteransichten oder in die Erstellung einer zweiten Ansicht auf ein Dokument.|  
|`m_pCurrentFrame`|`CFrameWnd*`|Das Rahmenfenster, auf dem zusätzliche Rahmenfenster modelliert werden, wie in der Erstellung eines zweiten Rahmenfensters auf einem Dokument.|  
  
 Wenn eine Normal\-Vorlage ein Dokument und die zugehörigen Komponenten erstellt, überprüft sie die Informationen, die in der `CCreateContext`\-Struktur gespeichert werden.  Beispielsweise sollte eine Ansicht nicht für ein nicht vorhandenes Dokument erstellt werden.  
  
> [!NOTE]
>  Alle Zeiger in `CCreateContext` sind optional und können `NULL` sein, wenn nicht angegeben oder unbekannt.  
  
 `CCreateContext` wird durch die Memberfunktionen verwendet, die unter "aufgeführt sind, finden auch". Schlagen Sie die Beschreibungen dieser Funktionen zu bestimmten Informationen nach, wenn Sie vorhaben, sie zu überschreiben.  
  
 Im Folgenden finden Sie einige allgemeine Richtlinien:  
  
-   Angeschlossen werden sollte wenn Sie übergeben werden, wie ein Argument für Fenstererstellung, wie in `CWnd::Create`, `CFrameWnd::Create` und `CFrameWnd::LoadFrame`, der erstellenskontext angibt, was das neue Fenster an.  Für die meisten Fenster ist die gesamte Struktur optional und ein `NULL` Zeiger kann übergeben werden.  
  
-   Für überschreibbare Memberfunktionen wie `CFrameWnd::OnCreateClient`, ist das `CCreateContext`\-Argument optional.  
  
-   Für die Memberfunktionen, die in Ansichtserstellung anfallen, müssen Sie über genügend Informationen bereitstellen, um die Ansicht zu erstellen.  Für die erste Ansicht in ein Splitterfenster, müssen Sie die Ansichtsklasseninformationen und das aktuelle Dokument enthalten.  
  
 Im Allgemeinen wenn Sie die Frameworkstandards verwenden, können Sie `CCreateContext` ignorieren.  Wenn Sie erweiterte Änderungen, Microsoft Foundation Class\-Bibliothek\-Quellcode versuchen, oder die Beispielprogramme, wie VIEWEX, führt Sie.  Wenn Sie einen erforderlichen Parameter vergessen, teilt eine Frameworkassertion beschrieben, was Sie vergessen haben.  
  
 Weitere Informationen zu `CCreateContext`, finden Sie im MFC\-Beispiel [VIEWEX](../../top/visual-cpp-samples.md).  
  
## Anforderungen  
 **Header:** afxext.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../Topic/CFrameWnd::Create.md)   
 [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)   
 [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)   
 [CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)   
 [CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)