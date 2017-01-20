---
title: "Ausnahmen: Ausnahmen in eigenen Funktionen ausl&#246;sen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausnahmen, Auslösen"
  - "Funktionen [C++], Auslösen von Ausnahmen"
  - "Auslösen von Ausnahmen, from-Funktionen"
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmen: Ausnahmen in eigenen Funktionen ausl&#246;sen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es ist möglich, das MFC\-Ausnahmebehandlungsparadigma nur zu verwenden, um Ausnahmen abzufangen, die von Funktionen in MFC oder anderen Bibliotheken ausgelöst werden.  Neben den ob Ausnahmen, die durch Bibliothekscode ausgelöst werden, können Sie Ausnahmen aus dem eigenen Code auslösen, wenn Funktionen schreiben, die mit Bedingungen auftreten können.  
  
 Wenn eine Ausnahme ausgelöst wird, wird die Ausführung der aktuellen Funktion beendet und springt direkt zum **catch**\-Block der innersten Ausnahmeframe.  Der Ausnahmemechanismus umgeht den normalen Beendigungspfad einer Funktion.  Daher müssen Sie sicherstellen, diese Speicherblöcke zu löschen, die in einer normalen Beendigung gelöscht werden.  
  
#### Wenn Sie eine Ausnahme auslösen  
  
1.  Verwenden Sie eine der MFC\-Hilfsfunktionen, wie `AfxThrowMemoryException`.  Diese Funktionen lösen ein zugeteiltes Ausnahmeobjekt des entsprechenden Typs aus.  
  
     Im folgenden Beispiel versucht, eine Funktion zwei Speicherblöcken zuzuordnen und löst eine Ausnahme aus, wenn eine Zuordnung fehlschlägt:  
  
     [!CODE [NVC_MFCExceptions#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#17)]  
  
     Wenn die erste Zuordnung fehlschlägt, können Sie die Arbeitsspeicherausnahme einfach auslösen.  Wenn die erste Zuordnung erfolgreich ist, aber zweite fehlschlägt, müssen Sie dem ersten Zuordnungsblock freigeben, bevor die Ausnahme auslösen.  Wenn beide Zuordnungen folgen, können Sie normalerweise fortfahren und Blöcken freigeben, wenn Sie die Funktion beenden.  
  
     – oder –  
  
2.  Verwenden Sie eine benutzerdefinierte Ausnahme, um einer Problemzustand anzugeben.  Sie können ein Element eines beliebigen Typs, selbst eine ganze Klasse, als die Ausnahme auslösen.  
  
     Im folgenden Beispiel versucht, einen Sound von einem Wellengerät wiederzugeben und löst eine Ausnahme aus, wenn ein Fehler auftritt.  
  
     [!CODE [NVC_MFCExceptions#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#18)]  
  
> [!NOTE]
>  Standardabwicklung MFC Ausnahmen gilt nur auf Zeiger zu `CException`\-Objekten zu \(und Objekten von `CException` abgeleitete Klassen\).  Die Ausnahmeder durch die Überbrückungen MFC des oben stehenden Beispiels.  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)