---
title: 'Multithreading: Beenden von Threads | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
f1_keywords:
- CREATE_SUSPENDED
dev_langs:
- C++
helpviewer_keywords:
- premature thread termination
- starting threads
- threading [MFC], terminating threads
- multithreading [C++], terminating threads
- threading [C++], stopping threads
- terminating threads
- stopping threads
- AfxEndThread method
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdf9376e9f8c9e9d74d88d0bef40dc71fd43d51f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-terminating-threads"></a>Multithreading: Beenden von Threads
In den beiden folgenden Fällen wird die Beendigung eines Threads ordnungsgemäß ausgelöst: die Steuerungsfunktion wird beendet, oder der Thread darf nicht vollständig ausgeführt werden. Falls z. B. in einem Textverarbeitungsprogramm ein Thread für den Hintergrunddruck verwendet wird, wird die Steuerungsfunktion normal beendet, sobald der Druckauftrag erfolgreich abgeschlossen ist. Wenn der Benutzer den Druckvorgang jedoch abbrechen möchte, muss der Thread für den Hintergrunddruck vorzeitig beendet werden. In diesem Thema wird beschrieben, wie jede Situation zu implementieren ist und wie der Exitcode des Threads nach seiner Beendigung ermittelt wird.  
  
-   [Normale Threadbeendigung](#_core_normal_thread_termination)  
  
-   [Vorzeitige Threadbeendigung](#_core_premature_thread_termination)  
  
-   [Abfragen des Exitcodes eines Threads](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> Normale Threadbeendigung  
 Von einem Arbeitsthread werden bei der normalen Threadbeendigung folgende einfache Schritte ausgeführt: die Steuerungsfunktion wird beendet und es wird ein Wert zurückgegeben, aus dem der Grund für die Beendung hervorgeht. Verwenden Sie entweder die [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) Funktion oder eine `return` Anweisung. Normalerweise steht 0 für die erfolgreiche Ausführung; dies ist ganz Ihnen überlassen.  
  
 Für einen Benutzeroberflächenthread ist der Vorgang ebenso einfach: aus den Benutzeroberflächenthread aufgerufen [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Der einzige Parameter, **PostQuitMessage** nimmt ist der Exitcode des Threads. Bei Arbeitsthreads steht 0 normalerweise für eine erfolgreiche Ausführung.  
  
##  <a name="_core_premature_thread_termination"></a> Vorzeitige Threadbeendigung  
 Vorzeitige Beendigung eines Threads ist ähnlich einfach: Rufen Sie [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) von innerhalb des Threads. Übergeben Sie den gewünschten Exitcode als einzigen Parameter. Hierdurch wird die Ausführung des Threads beendet, der Stapel des Threads freigegeben, alle mit dem Thread verbundenen DLLs getrennt und das Threadobjekt aus dem Speicher gelöscht.  
  
 `AfxEndThread` muss von dem zu beendenden Thread aus aufgerufen werden. Wenn Sie einen Thread von einem anderen Thread aus beenden möchten, müssen Sie ein Kommunikationsverfahren zwischen den beiden Threads einrichten.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Abfragen des Exitcodes eines Threads  
 Um den Exitcode des Arbeits- oder den Benutzeroberflächenthread zu erhalten, rufen die [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190) Funktion. Weitere Informationen zu dieser Funktion finden Sie im [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Für diese Funktion sind das Handle für den Thread (im `m_hThread`-Datenmember des `CWinThread`-Objekts gespeichert) und die Adresse eines `DWORD` erforderlich.  
  
 Wenn der Thread weiterhin aktiv ist, wird **GetExitCodeThread** platziert **GetExitCodeThread** im bereitgestellten `DWORD` Adresse; andernfalls wird der Exitcode in dieser Adresse platziert.  
  
 Abfragen des Exitcodes von [CWinThread](../mfc/reference/cwinthread-class.md) Objekte ist ein zusätzlicher Schritt. Standardmäßig wird bei Beendung eines `CWinThread`-Threads das entsprechende Threadobjekt gelöscht. Dies bedeutet, dass Sie nicht mehr auf den `m_hThread`-Datenmember zugreifen können, da das `CWinThread`-Objekt nicht mehr vorhanden ist. Führen Sie zur Vermeidung dieser Situation einen der folgenden Schritte aus:  
  
-   Legen Sie die `m_bAutoDelete` Datenmember **"false"**. Auf diese Weise ist ein `CWinThread`-Objekt auch nach dem Beenden des Threads noch vorhanden. Sie können dann auf den `m_hThread`-Datenmember zugreifen, nachdem der Thread beendet wurde. Bei dieser Methode müssen Sie das Zerstören des `CWinThread`-Objekts selbst übernehmen, da es nicht automatisch vom Framework gelöscht wird. Dies ist die bevorzugte Methode.  
  
-   Speichern Sie das Handle des Threads separat. Kopieren Sie nach der Erstellung des Threads, dessen `m_hThread` Datenmember (mit **:: DuplicateHandle**) einer anderen Variablen und über diese Variable darauf zugreifen. Auf diese Weise wird das Objekt automatisch bei Beendigung gelöscht, und Sie haben dennoch die Möglichkeit, den Grund für die Beendigung des Threads zu ermitteln. Achten Sie darauf, dass der Thread nicht beendet wird, bevor Sie die Möglichkeit hatten, das Handle zu duplizieren. Die sicherste Möglichkeit hierzu ist die Übergabe **CREATE_SUSPENDED** auf [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), das Handle speichern, und klicken Sie dann die Ausführung des Threads durch Aufrufen [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread).  
  
 Bei beiden Methoden lässt sich ermitteln, warum ein `CWinThread`-Objekt beendet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading mit C++ und MFC](../parallel/multithreading-with-cpp-and-mfc.md)   
 [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)