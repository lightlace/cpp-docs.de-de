---
title: Häufig gestellte Fragen zu MFC-DLL
ms.date: 11/04/2016
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: 17acde51d3fa9a7fabf14de748fd60b126b8b8f3
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418840"
---
# <a name="dll-frequently-asked-questions"></a>FAQ (Häufig gestellte Fragen) zu DLLs

Folgenden werden einige häufig gestellte für Fragen (FAQ) zu DLLs.

- [Kann eine MFC-DLL mehrere Threads erstellen?](#mfc_multithreaded_1)

- [Kann eine Multithreadanwendung eine MFC-DLL in unterschiedlichen Threads zugreifen?](#mfc_multithreaded_2)

- [Gibt es alle MFC-Klassen oder Funktionen, die in einer MFC-DLL nicht verwendet werden?](#mfc_prohibited_classes)

- [Welche Optimierungstechniken sollte ich zur leistungsverbesserung beim Laden der Anwendung verwenden?](#mfc_optimization)

- [Ein Arbeitsspeicherverlust in der regulären MFC DLL vorhanden ist, aber Code scheint in Ordnung. Wie finde ich den Speicherverlust?](#memory_leak)

## <a name="mfc_multithreaded_1"></a> Kann eine MFC-DLL mehrere Threads erstellen?

Mit der Ausnahme während der Initialisierung einer MFC-DLL problemlos mehrere Threads erstellen können, solange er die Win32-Thread verwendet lokaler Speicher (TLS) wie Funktionen **TlsAlloc** lokalen Threadspeicher zugewiesen werden. Aber wenn eine MFC-DLL verwendet **__declspec(thread)** zum Zuordnen der threadlokale Speicher die Clientanwendung muss werden implizit mit der DLL verknüpft. Wenn die Client-Anwendung explizit auf die DLL, die den Aufruf von verknüpft **LoadLibrary** wird die DLL nicht erfolgreich geladen. Weitere Informationen zu den Thread-lokalen Variablen in DLLs, finden Sie unter [Thread](../cpp/thread.md).

Eine MFC-DLL, die einen neuen MFC-Thread während des Starts erstellt wird reagiert, wenn sie von einer Anwendung geladen wird. Dies schließt, wenn ein Thread, durch den Aufruf erstellt wird `AfxBeginThread` oder `CWinThread::CreateThread` in:

- Die `InitInstance` von einem `CWinApp`-abgeleitetes Objekt in einer regulären MFC-DLL.

- Einer angegebenen `DllMain` oder **RawDllMain** Funktion in einer regulären MFC-DLL.

- Einer angegebenen `DllMain` oder **RawDllMain** -Funktion in einer MFC-Erweiterungs-DLL.

## <a name="mfc_multithreaded_2"></a> Kann eine Multithreadanwendung eine MFC-DLL in unterschiedlichen Threads zugreifen?

Multithread-Anwendungen können reguläre MFC-DLLs, die dynamisch mit MFC verknüpft und MFC-Erweiterungs-DLLs aus verschiedenen Threads zugreifen. Und eine Anwendung stehen seit Visual C++, Version 4.2, reguläre MFC-DLLs, die von mehreren Threads, die in der Anwendung erstellten statisch mit MFC verknüpft.

Vor Version 4.2 konnte nur von einem externer Thread mit einer regulären MFC DLL angefügt werden, die statisch mit MFC verknüpft.

Beachten Sie, die den Begriff USRDLL nicht mehr in der Dokumentation zu Visual C++ verwendet wird. Eine reguläre MFC-DLL, die statisch mit MFC verknüpfte hat dieselben Merkmale wie die frühere USRDLL.

## <a name="mfc_prohibited_classes"></a> Gibt es alle MFC-Klassen oder Funktionen, die in einer MFC-DLL nicht verwendet werden?

Verwenden von Erweiterungs-DLLs der `CWinApp`-abgeleitete Klasse von der Clientanwendung. Es müssen keine eigene `CWinApp`-abgeleitete Klasse.

reguläre MFC-DLLs müssen eine `CWinApp`-Klasse und ein einzelnes Objekt der Anwendungsklasse abgeleitet, wie eine MFC-Anwendung. Im Gegensatz zu den `CWinApp` Objekt einer Anwendung, die `CWinApp` Objekt der DLL keine Haupt-Meldungsverteilschleife.

Beachten Sie, dass die `CWinApp::Run` Mechanismus gelten nicht für eine DLL, die Anwendung besitzt die Haupt-Meldungsverteilschleife. Wenn die DLL nicht modale Dialogfelder geöffnet oder eine eigene Hauptrahmenfenster, muss der Anwendung Haupt-Meldungsverteilschleife eine Routine, die von der DLL, die wiederum aufruft exportierten Aufrufen der `CWinApp::PreTranslateMessage` Memberfunktion des DLL Application-Objekt.

## <a name="mfc_optimization"></a> Welche Optimierungstechniken sollte ich verwenden, um die Client-Anwendung zu verbessern&#39;s Leistung beim Laden?

Ist die DLL eine reguläre MFC-DLL, die statisch mit MFC, ändern ihn in eine reguläre verknüpft ist reduziert, die dynamisch mit MFC verknüpfte MFC-DLL die Dateigröße an.

Wenn die DLL zahlreiche exportierte Funktionen aufweist, verwenden Sie eine DEF-Datei, die Funktionen exportiert (anstelle von **__declspec(dllexport)**) und verwenden Sie die DEF-Datei [NONAME-Attribut](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) auf jedem exportierten Funktionen. Das NONAME-Attribut bewirkt, dass nur der Ordinalwert und nicht der Funktionsname in der Exporttabelle der DLL, gespeichert werden, wodurch die Dateigröße reduziert wird.

DLLs, die implizit mit einer Anwendung verknüpft sind werden geladen, wenn die Anwendung geladen wird. Versuchen Sie zur Verbesserung der Leistung beim Laden, unterteilen die DLL in verschiedenen DLLs aus. Legen Sie alle Funktionen, die die aufrufende Anwendung unmittelbar nach dem Laden in eine DLL-Datei muss ein, und haben Sie die aufrufende Anwendung, die implizit mit dieser DLL verknüpft. Fügen Sie die anderen Funktionen, die nicht sofort die aufrufende Anwendung benötigt in eine andere DLL und haben die Anwendung explizit auf diese DLL verknüpfen. Weitere Informationen finden Sie unter [bestimmen welche Verknüpfungsmethode](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use).

## <a name="memory_leak"></a> Es&#39;s eines Speicherverlusts in der regulären MFC DLL, aber mein Code sieht gut aus. Wie finde ich den Speicherverlust?

Eine mögliche Ursache für den Speicherverlust ist, dass MFC temporäre Objekte erstellt, die innerhalb von Meldungshandlerfunktionen verwendet werden. In MFC-Anwendungen, diese temporären Objekte werden automatisch bereinigt die `CWinApp::OnIdle()` -Funktion, die zwischen der Verarbeitung von Nachrichten aufgerufen wird. Im MFC-Dynamic Link Libraries (DLLs), aber die `OnIdle()` Funktion wird nicht automatisch aufgerufen. Daher sind temporäre Objekte nicht automatisch bereinigt. Um temporäre Objekte bereinigen, die DLL muss explizit aufrufen, `OnIdle(1)` in regelmäßigen Abständen.

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)
