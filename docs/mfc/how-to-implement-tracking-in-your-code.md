---
title: "Gewusst wie: Implementieren der Nachverfolgung im Code | Microsoft Docs"
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
  - "CRectTracker-Klasse, Implementieren von Trackern"
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Gewusst wie: Implementieren der Nachverfolgung im Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein OLE\-Element nachzuverfolgen, müssen Sie bestimmte Ereignisse behandeln, die auf das Element, beispielsweise durch Klicken auf das Element oder Aktualisieren des Dokuments verknüpft werden.  In allen Fällen ist es ausreichend, ein temporäres [CRectTracker](../mfc/reference/crecttracker-class.md)\-Objekt deklariert und das Element mithilfe dieses Objekts zu bearbeiten.  
  
 Wenn ein Benutzer ein Element auswählt oder ein Objekt mit einem Menübefehl einfügt, müssen Sie den Protokollierer mit den korrekten Formaten initialisieren, um den Zustand des OLE\-Elements darzustellen.  In der folgenden Tabelle werden die Konventionen, die durch das OCLIENT\-Beispiel verwendet werden.  Weitere Informationen über diese formatiert, sieht `CRectTracker`.  
  
### Container\-Formate und Zustände des OLE\-Elements  
  
|Format angezeigt|Zustand des OLE\-Elements|  
|----------------------|-------------------------------|  
|Graugelber Breitflügelspanner|Element verknüpft wird|  
|Ausgefüllter Rahmen|Element wird im Dokument eingebettet|  
|Ziehpunkte|Element ist derzeit ausgewählt|  
|Schraffierter Rahmen|Element ist einfach direkt aktiviert|  
|Muster, schraffierend überlagert Element|Der Server des Elements ist geöffnet|  
  
 Sie können die Initialisierung mit einer Prozedur bearbeiten, die den Zustand des OLE\-Elements untersucht und die entsprechenden Stile festlegen.  **SetupTracker** Die Funktion, die im OCLIENT\-Beispiel gefunden wird, zeigt Protokolliererinitialisierung.  Die Parameter dieser Funktion sind die Adresse des Protokollierers, *pTracker*; ein Zeiger z Clientelement, das z Protokollierer bezieht, `pItem`; und ein Zeiger auf ein Rechteck, *pTrueRect*.  Weitere Informationen finden vollständiges Beispiel dieser Funktion, das Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE.  
  
 Das **SetupTracker** Codebeispiel stellt eine einzelne Funktion dar; Zeilen der Funktion werden mit Informationen über die Funktionen der Funktion vermischt werden:  
  
 [!CODE [NVC_MFCOClient#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOClient#1)]  
  
 Der Protokollierer wird initialisiert, indem die minimale Größe festgelegt und das Format des Protokollierers löscht.  
  
 [!CODE [NVC_MFCOClient#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOClient#2)]  
  
 Die folgenden Zeilen überprüfen, um festzustellen, ob das Element nur ausgewählt wird und ob das Element dem Dokument verknüpft ist oder im Element eingebettet.  Die Ziehpunkte auf der Innenseite des Rahmens werden in den Stil hinzugefügt und angeben, dass das Element derzeit ausgewählt ist.  Wenn das Element dem Dokument verknüpft ist, wird das Graugelber Breitflügelspanner\-Format verwendet.  Ein durchgehender Kontext wird verwendet, wenn das Element eingebettet wird.  
  
 [!CODE [NVC_MFCOClient#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOClient#3)]  
  
 Der folgende Code überlagert das Element mit einer Schraffur, wenn das Element geöffnet ist.  
  
 [!CODE [NVC_MFCOClient#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOClient#4)]  
  
 Sie können diese Funktion dann aufrufen, wenn der Protokollierer angezeigt werden muss.  Beispielsweise rufen Sie die Funktion von der `OnDraw`\-Funktion der Ansichtsklasse auf.  Dies aktualisiert die Darstellung des Protokollierers, wenn die Ansicht neu gestrichelt ist.  Ein vollständiges Beispiel finden Sie die Funktion **CMainView::OnDraw** des Beispiels [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE.  
  
 In der Anwendung werden Ereignisse, die Protokollierercode, wie Größenanpassung benötigen und wechseln oder der erkennende Treffer, auf.  Diese Aktionen geben normalerweise an, dass versucht wird, das Element zu erfassen oder verschieben gemacht wird.  In diesen Fällen müssen Sie festlegen, was gegriffen wurde: Ziehpunkt oder ein Teil des Rahmens zwischen Ziehpunkten.  Der `OnLButtonDown` \- Meldungshandler eignet sich gut, der die Position der Maus in Bezug auf das Element zu testen.  Führen Sie `CRectTracker::HitTest` einen Aufruf.  Wenn der Test einige Ausnahme **CRectTracker::hitOutside** zurückgibt, wird das Element angepasst oder verschoben.  Daher sollten Sie die Memberfunktion `Track` machen.  Siehe die **CMainView::OnLButtonDown**\-Funktion im Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE für ein vollständiges Beispiel.  
  
 Die `CRectTracker`\-Klasse stellt verschiedene Cursor\-Formen, die verwendet werden, um anzugeben, ob ein Verschiebevorgang, Größe ändern, oder Ziehvorgang statt.  Um dieses Ereignis behandeln, Überprüfung, um festzustellen, ob das Element direkt unter der Maus ausgewählt ist.  Wenn es ist, führen Sie `CRectTracker::SetCursor` einen Aufruf, oder Sie rufen den Standardhandler auf.  Im folgenden Beispiel ist vom Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE:  
  
 [!CODE [NVC_MFCOClient#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCOClient#5)]  
  
## Siehe auch  
 [Tracker: Implementieren von Trackern in einer OLE\-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)