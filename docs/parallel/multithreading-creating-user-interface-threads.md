---
title: "Multithreading: Erstellen von Benutzeroberflächenthreads | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 105685e0db4689978ef1e6f8615bb5e5f8acdd43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-creating-user-interface-threads"></a>Multithreading: Erstellen von Benutzeroberflächenthreads
Ein Benutzeroberflächenthread wird normalerweise verwendet, um unabhängig von Threads, die derzeit andere Teile der Anwendung ausführen, Benutzereingaben zu behandeln und um auf vom Benutzer generierte Ereignisse zu reagieren. Der Thread der Hauptanwendung, der in der von `CWinApp` abgeleiteten Klasse enthalten ist, ist bereits erstellt und wird automatisch gestartet. In diesem Thema werden die notwendigen Schritte zur Erstellung zusätzlicher Benutzeroberflächenthreads beschrieben.  
  
 Als Erstes müssen Sie beim Erstellen eines Threads für die Benutzeroberfläche wird beim Ableiten einer Klasse von [CWinThread](../mfc/reference/cwinthread-class.md). Sie deklarieren und implementieren Sie dies müssen-Klasse unter Verwendung der [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) und [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) Makros. Die Klasse muss bestimmte Funktionen überschreiben und kann wiederum andere Funktionen überschreiben. Diese Funktionen und ihre Aufgaben werden in der folgenden Tabelle erläutert.  
  
### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Zu überschreibende Funktionen bei der Erstellung eines Benutzeroberflächenthreads  
  
|Funktion|Zweck|  
|--------------|-------------|  

|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)| Cleanup ausgeführt, wenn der Thread beendet wird. In der Regel außer Kraft gesetzt. |  
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)| Führen Sie die instanzeninitialisierung des Threads. Muss überschrieben werden. |  
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)| Führen Sie die threadspezifische leerlaufzeitverarbeitung. Wird normalerweise nicht überschrieben. |  
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)| Nachrichten zu filtern, bevor sie an verteilt wurden **TranslateMessage** und **DispatchMessage**. Wird normalerweise nicht überschrieben. |  
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)| Abgefangen Sie durch den Thread Meldungs- und befehlshandlern nicht behandelte Ausnahmen werden. Wird normalerweise nicht überschrieben. |  
|[Führen Sie](../mfc/reference/cwinthread-class.md#run)| Steuerungsfunktion für den Thread. Enthält die Meldungsverteilschleife. Wird selten überschrieben. |  

  
 in MFC werden durch Parameterüberladung zwei Versionen von `AfxBeginThread` zur Verfügung gestellt: eine, die nur Arbeitsthreads erstellen kann, und eine, die Benutzeroberflächenthreads oder Arbeitsthreads erstellen kann. Um Ihre Benutzeroberflächenthread zu starten, rufen Sie die zweite Überladung der [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), die folgenden Informationen angeben:  
  
-   Die [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) die Sie von abgeleiteten Klasse `CWinThread`.  
  
-   (Optional) Die gewünschte Prioritätsebene Standardmäßig ist normale Priorität eingestellt. Weitere Informationen zu den verfügbaren Prioritätsebenen finden Sie unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
-   (Optional) Die gewünschte Stapelgröße für den Thread. Standardmäßig wird die Größe des Erstellungsthreads verwendet.  
  
-   (Optional) **CREATE_SUSPENDED** , wenn der Thread in einem angehaltenen Zustand erstellt werden soll. Standardmäßig ist 0 eingestellt; Sie können den Thread auch normal starten.  
  
-   (Optional) Die gewünschten Sicherheitsattribute Standardmäßig werden dieselben Zugriffsrechte wie für den übergeordneten Thread verwendet. Weitere Informationen zum Format dieser Sicherheitsinformationen finden Sie unter [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Von `AfxBeginThread` wird der Großteil der Arbeit für Sie übernommen: Erstellt ein neues Objekt der Klasse, initialisiert es mit den Informationen, die Sie angeben, ruft [CWinThread:: CreateThread](../mfc/reference/cwinthread-class.md#createthread) um den Thread zu starten. Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Multithreading: Beenden von Threads](../parallel/multithreading-terminating-threads.md)  
  
-   [Multithreading: Erstellen von Arbeitsthreads](../parallel/multithreading-creating-worker-threads.md)  
  
-   [Prozesse und Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md)