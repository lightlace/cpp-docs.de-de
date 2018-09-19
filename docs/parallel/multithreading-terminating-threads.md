---
title: 'Multithreading: Beenden von Threads in MFC | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: 1bd8abd7971c112f0d9e872df73b431c78259981
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205421"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>Multithreading: Beenden von Threads in MFC
In den beiden folgenden Fällen wird die Beendigung eines Threads ordnungsgemäß ausgelöst: die Steuerungsfunktion wird beendet, oder der Thread darf nicht vollständig ausgeführt werden. Falls z. B. in einem Textverarbeitungsprogramm ein Thread für den Hintergrunddruck verwendet wird, wird die Steuerungsfunktion normal beendet, sobald der Druckauftrag erfolgreich abgeschlossen ist. Wenn der Benutzer den Druckvorgang jedoch abbrechen möchte, muss der Thread für den Hintergrunddruck vorzeitig beendet werden. In diesem Thema wird beschrieben, wie jede Situation zu implementieren ist und wie der Exitcode des Threads nach seiner Beendigung ermittelt wird.  
  
- [Normale Threadbeendigung](#_core_normal_thread_termination)  
  
- [Vorzeitige Threadbeendigung](#_core_premature_thread_termination)  
  
- [Zum Abrufen des Exitcodes eines Threads](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> Normale Threadbeendigung  
 
Von einem Arbeitsthread werden bei der normalen Threadbeendigung folgende einfache Schritte ausgeführt: die Steuerungsfunktion wird beendet und es wird ein Wert zurückgegeben, aus dem der Grund für die Beendung hervorgeht. Verwenden Sie entweder die [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) Funktion oder ein **zurückgeben** Anweisung. Normalerweise steht 0 für die erfolgreiche Ausführung; dies ist ganz Ihnen überlassen.  
  
Der Prozess für einen UI-Thread ist ebenso einfach: innerhalb von den Benutzeroberflächen-Thread aufgerufen werden [PostQuitMessage](https://msdn.microsoft.com/library/windows/desktop/ms644945) im Windows SDK. Der einzige Parameter, die `PostQuitMessage` ist der Exitcode des Threads. Bei Arbeitsthreads steht 0 normalerweise für eine erfolgreiche Ausführung.  
  
##  <a name="_core_premature_thread_termination"></a> Vorzeitige Threadbeendigung  
 
Vorzeitige Beendigung eines Threads ist beinahe ebenso einfach: Rufen Sie [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) von innerhalb des Threads. Übergeben Sie den gewünschten Exitcode als einzigen Parameter. Hierdurch wird die Ausführung des Threads beendet, der Stapel des Threads freigegeben, alle mit dem Thread verbundenen DLLs getrennt und das Threadobjekt aus dem Speicher gelöscht.  
  
`AfxEndThread` muss von dem zu beendenden Thread aus aufgerufen werden. Wenn Sie einen Thread von einem anderen Thread aus beenden möchten, müssen Sie ein Kommunikationsverfahren zwischen den beiden Threads einrichten.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Zum Abrufen des Exitcodes eines Threads  
 
Rufen Sie zum Abrufen des Exitcodes des Arbeits- oder der Benutzeroberflächenthread der [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread) Funktion. Informationen zu dieser Funktion finden Sie im Windows SDK. Diese Funktion sind das Handle für den Thread (gespeichert der `m_hThread` -Datenmember des `CWinThread` Objekte) und die Adresse eines DWORD.  
  
Wenn der Thread weiterhin aktiv ist, ist `GetExitCodeThread` STILL_ACTIVE platziert, in der angegebenen DWORD-Adresse; andernfalls wird der Exitcode in dieser Adresse angeordnet.  
  
Zum Abrufen des Exitcodes von [CWinThread](../mfc/reference/cwinthread-class.md) Objekte ist ein zusätzlicher Schritt. Standardmäßig wird bei Beendung eines `CWinThread`-Threads das entsprechende Threadobjekt gelöscht. Dies bedeutet, dass Sie nicht mehr auf den `m_hThread`-Datenmember zugreifen können, da das `CWinThread`-Objekt nicht mehr vorhanden ist. Führen Sie zur Vermeidung dieser Situation einen der folgenden Schritte aus:  
  
- Legen Sie die `m_bAutoDelete` -Datenmember auf "false". Auf diese Weise ist ein `CWinThread`-Objekt auch nach dem Beenden des Threads noch vorhanden. Sie können dann auf den `m_hThread`-Datenmember zugreifen, nachdem der Thread beendet wurde. Bei dieser Methode müssen Sie das Zerstören des `CWinThread`-Objekts selbst übernehmen, da es nicht automatisch vom Framework gelöscht wird. Dies ist die bevorzugte Methode.  
  
- Speichern Sie das Handle des Threads separat. Nachdem der Thread erstellt wurde, kopieren Sie die `m_hThread` -Datenmember (mit `::DuplicateHandle`) in eine andere Variable und greifen sie über die Variable. Auf diese Weise wird das Objekt automatisch bei Beendigung gelöscht, und Sie haben dennoch die Möglichkeit, den Grund für die Beendigung des Threads zu ermitteln. Achten Sie darauf, dass der Thread nicht beendet wird, bevor Sie die Möglichkeit hatten, das Handle zu duplizieren. Die sicherste Möglichkeit hierzu ist CREATE_SUSPENDED zu übergeben [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), das Handle speichern, und klicken Sie dann die Ausführung des Threads durch Aufruf [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread).  
  
Bei beiden Methoden lässt sich ermitteln, warum ein `CWinThread`-Objekt beendet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 
[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)   
[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
[ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread)