---
title: "Ausnahmen: Freigeben von Objekten in Ausnahmen | Microsoft Docs"
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
  - "Zerstören von Objekten"
  - "Ausnahmebehandlung, Zerstören von Objekten"
  - "Befreien von Objekten"
  - "lokale Ausnahmebehandlung"
  - "Speicherverluste, von Ausnahme verursacht"
  - "Auslösen von Ausnahmen, nach der Zerstörung"
  - "Auslösen von Ausnahmen, Befreien von Objekten in Ausnahmen"
  - "try-catch-Ausnahmebehandlung, Zerstören von Objekten"
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausnahmen: Freigeben von Objekten in Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Anforderung und die Möglichkeit der Freigabe von Objekten, wenn eine Ausnahme auftritt.  Folgende Themen werden behandelt:  
  
-   [Die Ausnahme lokal behandeln](#_core_handling_the_exception_locally)  
  
-   [Ausnahmen auslösen, nachdem die Objekte zerstört wurden](#_core_throwing_exceptions_after_destroying_objects)  
  
 Ausnahmen, die vom Framework oder von der Anwendung ausgelöst werden, unterbrechen normalen Ablaufsteuerung.  Deshalb ist es sehr wichtig, nah Objekte nachverfolgen, damit sie ordnungsgemäß zu entfernen können, wenn eine Ausnahme ausgelöst wird.  
  
 Es gibt zwei primäre Möglichkeiten, um dazu.  
  
-   Behandeln lokal unter Verwendung der **try** und **catch** Schlüsselwörter, zerstören anschließend alle Objekte mit einer Anweisung.  
  
-   Zerstören Sie dies im **catch**\-Block, bevor die Ausnahme den Blocks für weitere Behandlung auslösen.  
  
 Diese zwei Ansätze werden unten als Lösungen zum problematischen folgenden Beispiel veranschaulicht:  
  
 [!CODE [NVC_MFCExceptions#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#14)]  
  
 Wie oben geschrieben, wird `myPerson` nicht gelöscht, wenn eine Ausnahme von `SomeFunc` ausgelöst wird.  Die Ausführung springt direkt dem folgenden äußeren Ausnahmehandler Umgehung die Beendigung normaler Funktion und den Code, der das Objekt gelöscht werden.  Der Zeiger auf das Objekt den Gültigkeitsbereich verlässt, wenn die Ausnahme die Funktion verlässt, und der Arbeitsspeicher, der vom Objekt belegt wird, wird nicht wiederhergestellt, solange das Programm ausgeführt wird.  Dies ist ein Speicherverlust; daher erkannt, indem die die Speicherdiagnose verwendet.  
  
##  <a name="_core_handling_the_exception_locally"></a> Die Ausnahme lokal behandeln  
 Das **try\/catch** Paradigma stellt ein defensives Programmiertechniken zum Vermeiden von Speicherverlusten und dafür bereit, dass die Objekte zerstört werden, wenn Ausnahmen auftreten.  Beispielsweise kann das Beispiel, das oben in diesem Artikel gezeigt wurde, neu geschrieben werden, wie folgt:  
  
 [!CODE [NVC_MFCExceptions#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#15)]  
  
 Dieses neue diesem Beispiel werden einem Ausnahmehandler, um die Ausnahme abzufangen und lokal zu behandeln.  Es Beenden der Funktion und normalerweise zerstört das Objekt.  Der zentrale Aspekt dieses Beispiels ist, dass ein Kontext, um die Ausnahme abzufangen mit den **try\/catch** Blöcken eingerichtet wird.  Ohne lokale Ausnahmeframe wird die Funktion nie wissen, dass eine Ausnahme ausgelöst worden war und würde nicht die Möglichkeit haben normalerweise, zu beenden und das Objekt zu zerstören.  
  
##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> Ausnahmen auslösen, nachdem die Objekte zerstört wurden  
 Eine andere Methode, Ausnahmen behandeln ist, mit dem folgenden äußeren Ausnahmebehandlungskontext weiterzuleiten.  Dem **catch**\-Block können Sie eine Bereinigung der lokal zugeordneten Objekte durchführen und die Ausnahme zur weiteren Verarbeitung anschließend auslösen.  
  
 Das auslösende Funktion muss möglicherweise Heapobjekten freigeben.  Wenn die Funktion immer das Heapobjekt freigibt, bevor sie im Normalfall zurückkehrt, sollte die Funktion den Heapobjekt freigeben, bevor die Ausnahme auslöst.  Wenn die Funktion nicht normalerweise dem Objekt verwendet, bevor sie im Normalfall zurückkehrt, dann müssen Sie entscheiden, von Fall zu Fall dass das Heapobjekt freigegeben werden soll.  
  
 Das folgende Beispiel zeigt, wie lokal zugeordnete Objekte bereinigt werden können:  
  
 [!CODE [NVC_MFCExceptions#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#16)]  
  
 Der Ausnahmemechanismus gibt automatisch Frameobjekten frei; der Destruktor des Frameobjekts wird ebenfalls aufgerufen.  
  
 Wenn Sie Funktionen aufrufen, die Ausnahmen auslösen können, können Sie **try\/catch** Blöcke verwenden, um zu überprüfen, ob Sie die Ausnahmen abfangen und eine Möglichkeit haben, alle Objekte zu zerstören, die Sie erstellt haben.  Insbesondere Beachten Sie, dass viele MFC\-Funktionen Ausnahmen auslösen können.  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)