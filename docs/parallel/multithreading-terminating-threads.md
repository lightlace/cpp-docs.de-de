---
title: "Multithreading: Beenden von Threads"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxEndThread-Methode"
  - "Multithreading [C++], Terminieren von Threads"
  - "Vorzeitige Threadbeendigung"
  - "Starten von Threads"
  - "Anhalten von Threads"
  - "Terminieren von Threads"
  - "Threading [C++], Anhalten von Threads"
  - "Threading [MFC], Terminieren von Threads"
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading: Beenden von Threads
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den beiden folgenden Fällen wird die Beendigung eines Threads ordnungsgemäß ausgelöst: die Steuerungsfunktion wird beendet, oder der Thread darf nicht vollständig ausgeführt werden.  Falls z. B. in einem Textverarbeitungsprogramm ein Thread für den Hintergrunddruck verwendet wird, wird die Steuerungsfunktion normal beendet, sobald der Druckauftrag erfolgreich abgeschlossen ist.  Wenn der Benutzer den Druckvorgang jedoch abbrechen möchte, muss der Thread für den Hintergrunddruck vorzeitig beendet werden.  In diesem Thema wird beschrieben, wie jede Situation zu implementieren ist und wie der Exitcode des Threads nach seiner Beendigung ermittelt wird.  
  
-   [Normale Threadbeendigung](#_core_normal_thread_termination)  
  
-   [Vorzeitige Threadbeendigung](#_core_premature_thread_termination)  
  
-   [Abfragen des Exitcodes eines Threads](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> Normale Threadbeendigung  
 Von einem Arbeitsthread werden bei der normalen Threadbeendigung folgende einfache Schritte ausgeführt: die Steuerungsfunktion wird beendet und es wird ein Wert zurückgegeben, aus dem der Grund für die Beendung hervorgeht.  Sie können entweder die [AfxEndThread](../Topic/AfxEndThread.md)\-Funktion oder eine `return`\-Anweisung verwenden.  Normalerweise steht **0** für die erfolgreiche Ausführung; dies ist ganz Ihnen überlassen.  
  
 Für einen Benutzeroberflächenthread ist der Vorgang ebenso einfach: Vom Benutzeroberflächenthread aus wird [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] aufgerufen.  Der einzige für **PostQuitMessage** erforderliche Parameter ist der Exitcode des Threads.  Bei Arbeitsthreads steht **0** normalerweise für eine erfolgreiche Ausführung.  
  
##  <a name="_core_premature_thread_termination"></a> Vorzeitige Threadbeendigung  
 Die vorzeitige Beendigung eines Threads ist ähnlich einfach: Rufen Sie vom Thread aus [AfxEndThread](../Topic/AfxEndThread.md) auf.  Übergeben Sie den gewünschten Exitcode als einzigen Parameter.  Hierdurch wird die Ausführung des Threads beendet, der Stapel des Threads freigegeben, alle mit dem Thread verbundenen DLLs getrennt und das Threadobjekt aus dem Speicher gelöscht.  
  
 `AfxEndThread` muss von dem zu beendenden Thread aus aufgerufen werden.  Wenn Sie einen Thread von einem anderen Thread aus beenden möchten, müssen Sie ein Kommunikationsverfahren zwischen den beiden Threads einrichten.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Abfragen des Exitcodes eines Threads  
 Wenn Sie den Exitcode des Arbeits\- oder Benutzeroberflächenthreads ermitteln möchten, rufen Sie die [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)\-Funktion auf.  Weitere Informationen zu dieser Funktion finden Sie im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Für diese Funktion sind das Handle für den Thread \(im `m_hThread`\-Datenmember des `CWinThread`\-Objekts gespeichert\) und die Adresse eines `DWORD` erforderlich.  
  
 Wenn der Thread weiterhin aktiv ist, wird **STILL\_ACTIVE** von **GetExitCodeThread** in die bereitgestellte `DWORD`\-Adresse geschrieben; andernfalls wird der Exitcode in dieser Adresse geschrieben.  
  
 Zum Abrufen des Exitcodes von [CWinThread](../mfc/reference/cwinthread-class.md)\-Objekten ist ein zusätzlicher Schritt erforderlich.  Standardmäßig wird bei Beendung eines `CWinThread`\-Threads das entsprechende Threadobjekt gelöscht.  Dies bedeutet, dass Sie nicht mehr auf den `m_hThread`\-Datenmember zugreifen können, da das `CWinThread`\-Objekt nicht mehr vorhanden ist.  Führen Sie zur Vermeidung dieser Situation einen der folgenden Schritte aus:  
  
-   Legen Sie den `m_bAutoDelete`\-Datenmember auf **FALSE** fest.  Auf diese Weise ist ein `CWinThread`\-Objekt auch nach dem Beenden des Threads noch vorhanden.  Sie können dann auf den `m_hThread`\-Datenmember zugreifen, nachdem der Thread beendet wurde.  Bei dieser Methode müssen Sie das Zerstören des `CWinThread`\-Objekts selbst übernehmen, da es nicht automatisch vom Framework gelöscht wird.  Dies ist die bevorzugte Methode.  
  
-   Speichern Sie das Handle des Threads separat.  Kopieren Sie nach der Erstellung des Threads mit **::DuplicateHandle** dessen `m_hThread`\-Datenmember in eine andere Variable und greifen Sie über diese Variable darauf zu.  Auf diese Weise wird das Objekt automatisch bei Beendigung gelöscht, und Sie haben dennoch die Möglichkeit, den Grund für die Beendigung des Threads zu ermitteln.  Achten Sie darauf, dass der Thread nicht beendet wird, bevor Sie die Möglichkeit hatten, das Handle zu duplizieren.  Am effektivsten lässt sich dies verhindern, indem Sie **CREATE\_SUSPENDED** an [AfxBeginThread](../Topic/AfxBeginThread.md) übergeben, das Handle speichern und anschließend die Ausführung des Threads durch Aufruf von [ResumeThread](../Topic/CWinThread::ResumeThread.md) fortsetzen.  
  
 Bei beiden Methoden lässt sich ermitteln, warum ein `CWinThread`\-Objekt beendet wurde.  
  
## Siehe auch  
 [Multithreading mit C\+\+ und MFC](../parallel/multithreading-with-cpp-and-mfc.md)   
 [\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)