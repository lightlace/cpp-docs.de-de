---
title: 'Multithreading: Beenden von Threads in MFC'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
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
ms.openlocfilehash: 97a99eb2382c4864f1bd8cc881fab5e32a1e2070
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511708"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>Multithreading: Beenden von Threads in MFC

In den beiden folgenden Fällen wird die Beendigung eines Threads ordnungsgemäß ausgelöst: die Steuerungsfunktion wird beendet, oder der Thread darf nicht vollständig ausgeführt werden. Falls z. B. in einem Textverarbeitungsprogramm ein Thread für den Hintergrunddruck verwendet wird, wird die Steuerungsfunktion normal beendet, sobald der Druckauftrag erfolgreich abgeschlossen ist. Wenn der Benutzer den Druckvorgang jedoch abbrechen möchte, muss der Thread für den Hintergrunddruck vorzeitig beendet werden. In diesem Thema wird beschrieben, wie jede Situation zu implementieren ist und wie der Exitcode des Threads nach seiner Beendigung ermittelt wird.

- [Normale Thread Beendigung](#_core_normal_thread_termination)

- [Vorzeitige Beendigung des Threads](#_core_premature_thread_termination)

- [Abrufen des Exitcodes eines Threads](#_core_retrieving_the_exit_code_of_a_thread)

##  <a name="_core_normal_thread_termination"></a>Normale Thread Beendigung

Bei einem Arbeits Thread ist die normale Thread Beendigung einfach: Beenden Sie die Steuerungsfunktion, und geben Sie einen Wert zurück, der den Grund für die Beendigung angibt. Sie können entweder die [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) -Funktion oder eine **Return** -Anweisung verwenden. Normalerweise steht 0 für die erfolgreiche Ausführung; dies ist ganz Ihnen überlassen.

Bei einem Benutzeroberflächen Thread ist der Prozess genauso einfach: im Benutzeroberflächen Thread muss [PostQuitMessage](/windows/win32/api/winuser/nf-winuser-postquitmessage) im Windows SDK aufgerufen werden. Der einzige Parameter, `PostQuitMessage` der annimmt, ist der Exitcode des Threads. Bei Arbeitsthreads steht 0 normalerweise für eine erfolgreiche Ausführung.

##  <a name="_core_premature_thread_termination"></a>Vorzeitige Beendigung des Threads

Das vorzeitige Beenden eines Threads ist fast so einfach: Abrufen von [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) aus dem Thread. Übergeben Sie den gewünschten Exitcode als einzigen Parameter. Hierdurch wird die Ausführung des Threads beendet, der Stapel des Threads freigegeben, alle mit dem Thread verbundenen DLLs getrennt und das Threadobjekt aus dem Speicher gelöscht.

`AfxEndThread` muss von dem zu beendenden Thread aus aufgerufen werden. Wenn Sie einen Thread von einem anderen Thread aus beenden möchten, müssen Sie ein Kommunikationsverfahren zwischen den beiden Threads einrichten.

##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a>Abrufen des Exitcodes eines Threads

Um den Exitcode des Workers oder des Benutzeroberflächen Threads abzurufen, müssen Sie die [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread) -Funktion aufrufen. Weitere Informationen zu dieser Funktion finden Sie in der Windows SDK. Diese Funktion übernimmt das Handle für den Thread (im `m_hThread` Datenmember von `CWinThread` Objekten gespeichert) und die Adresse eines DWORD.

Wenn der Thread noch aktiv ist, `GetExitCodeThread` platziert STILL_ACTIVE in der angegebenen DWORD-Adresse; andernfalls wird der Exitcode in diese Adresse eingefügt.

Das Abrufen des Exitcodes von [CWinThread](../mfc/reference/cwinthread-class.md) -Objekten erfordert einen zusätzlichen Schritt. Standardmäßig wird bei Beendung eines `CWinThread`-Threads das entsprechende Threadobjekt gelöscht. Dies bedeutet, dass Sie nicht mehr auf den `m_hThread`-Datenmember zugreifen können, da das `CWinThread`-Objekt nicht mehr vorhanden ist. Führen Sie zur Vermeidung dieser Situation einen der folgenden Schritte aus:

- Legen Sie `m_bAutoDelete` den Datenmember auf false fest. Auf diese Weise ist ein `CWinThread`-Objekt auch nach dem Beenden des Threads noch vorhanden. Sie können dann auf den `m_hThread`-Datenmember zugreifen, nachdem der Thread beendet wurde. Bei dieser Methode müssen Sie das Zerstören des `CWinThread`-Objekts selbst übernehmen, da es nicht automatisch vom Framework gelöscht wird. Dies ist die bevorzugte Methode.

- Speichern Sie das Handle des Threads separat. Nachdem der Thread erstellt wurde, kopieren Sie `m_hThread` dessen Datenmember ( `::DuplicateHandle`mithilfe von) in eine andere Variable, und greifen Sie über diese Variable darauf zu. Auf diese Weise wird das Objekt automatisch bei Beendigung gelöscht, und Sie haben dennoch die Möglichkeit, den Grund für die Beendigung des Threads zu ermitteln. Achten Sie darauf, dass der Thread nicht beendet wird, bevor Sie die Möglichkeit hatten, das Handle zu duplizieren. Die sicherste Möglichkeit hierfür besteht darin, CREATE_SUSPENDED an [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)zu übergeben, das Handle zu speichern und dann den Thread durch Aufrufen von [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread)fortzusetzen.

Bei beiden Methoden lässt sich ermitteln, warum ein `CWinThread`-Objekt beendet wurde.

## <a name="see-also"></a>Siehe auch

[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread)
