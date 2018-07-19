---
title: MFC-DLL häufig gestellte Fragen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f5740989562aea799f3a49adfa464e2c460acb3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372509"
---
# <a name="dll-frequently-asked-questions"></a>FAQ (Häufig gestellte Fragen) zu DLLs  
  
Folgendes sind einige häufig gestellte für Fragen (FAQ) zu DLLs.  
    
-   [Kann eine MFC-DLL mehrere Threads erstellen?](#mfc_multithreaded_1)  

-   [Kann eine Multithreadanwendung auf eine MFC-DLL in unterschiedlichen Threads zugreifen?](#mfc_multithreaded_2)  
  
-   [Gibt es MFC-Klassen oder Funktionen, die in einer MFC-DLL verwendet werden können?](#mfc_prohibited_classes)  
  
-   [Welche Optimierungstechniken sollten werden verwendet, um die Leistung der Clientanwendung beim Laden zu verbessern?](#mfc_optimization)  
  
-   [Es ist ein Arbeitsspeicherverlust in der regulären MFC-DLL, aber mein Code einwandfrei. Wie finde ich den Speicherverlust?](#memory_leak)  

## <a name="mfc_multithreaded_1"></a> Kann eine MFC-DLL mehrere Threads erstellen?  
  
Außer während der Initialisierung einer MFC-DLL problemlos mehrere Threads erstellen kann als die Win32-Thread verwendet lokaler Speicher (TLS) wie Funktionen **TlsAlloc** lokalen Threadspeicher zugewiesen werden. Jedoch, wenn eine MFC-DLL verwendet **__declspec(thread)** um threadlokalen Speicher zu reservieren, die Clientanwendung muss werden implizit mit der DLL verknüpft. Wenn die Clientanwendung explizit mit der DLL, die den Aufruf von verknüpft **LoadLibrary** wird die DLL nicht erfolgreich geladen. Weitere Informationen zum Erstellen von mehreren Threads in MFC-DLLs finden Sie unter im Knowledge Base-Artikel "PRB: Aufrufen LoadLibrary() zum Laden einer DLL, verfügt über statische TLS" (Q118816). Weitere Informationen zu lokalen Variablen in DLLs finden Sie unter [Thread](../cpp/thread.md).
  
 Eine MFC-DLL, die während des Starts einen neuen MFC-Thread erstellt wird nicht mehr reagiert, wenn es von einer Anwendung geladen wird. Dies schließt, wenn ein Thread, durch den Aufruf erstellt wird `AfxBeginThread` oder `CWinThread::CreateThread` in:  
  
-   Die `InitInstance` von einem `CWinApp`-abgeleitetes Objekt in einer regulären MFC-DLL.  
  
-   Ein angegebenes `DllMain` oder **RawDllMain** Funktion in einer regulären MFC-DLL.  
  
-   Ein angegebenes `DllMain` oder **RawDllMain** -Funktion in einer MFC-Erweiterungs-DLL.  
  
 Weitere Informationen zum Erstellen von Threads während der Initialisierung finden Sie unter im Knowledge Base-Artikel "PRB: kann nicht erstellt eine MFC-Thread während der DLL Start" (Q142243).  
  
## <a name="mfc_multithreaded_2"></a> Kann eine Multithreadanwendung auf eine MFC-DLL in unterschiedlichen Threads zugreifen?
Multithreadanwendungen können reguläre MFC-DLLs, die dynamisch mit MFC verknüpft und MFC-Erweiterungs-DLLs aus unterschiedlichen Threads zugreifen. Und ab Visual C++, Version 4.2, eine Anwendung auf reguläre MFC-DLLs, die von mehreren Threads in der Anwendung erstellten statisch mit MFC verknüpft zugreifen kann.  
  
 Vor Version 4.2 konnte nur über einen externen Thread in eine reguläre MFC-DLL angefügt werden, die statisch mit MFC verknüpft. Weitere Informationen zu Einschränkungen, die Zugriff auf reguläre MFC-DLLs, die von mehreren Threads (vor Visual C++, Version 4.2) statisch mit MFC verknüpft wird, finden Sie unter im Knowledge Base-Artikel "mehrere Threads und MFC _USRDLLs" (Q122676).  
  
 Beachten Sie, die den Begriff USRDLL nicht mehr in der Dokumentation zu Visual C++ verwendet wird. Eine reguläre MFC-DLL, die statisch mit MFC verknüpft wird, hat dieselben Merkmale wie die frühere USRDLL.  


## <a name="mfc_prohibited_classes"></a> Gibt es MFC-Klassen oder Funktionen, die in einer MFC-DLL verwendet werden können?
Erweiterungs-DLLs verwenden die `CWinApp`-abgeleitete Klasse von der Clientanwendung. Sie dürfen keine eigene `CWinApp`-Klasse.  
  
Reguläre MFC-DLLs benötigen eine `CWinApp`-Klasse und ein einzelnes Objekt dieser Anwendungsklasse abgeleitet, wie eine MFC-Anwendung. Im Gegensatz zu den `CWinApp` Objekt einer Anwendung die `CWinApp` Objekt der DLL keine Haupt-Meldungsverteilschleife.  
  
 Beachten Sie, dass, weil die `CWinApp::Run` Mechanismus gilt nicht für eine DLL, die Anwendung besitzt die Haupt-Meldungsverteilschleife. Wenn die DLL nicht modale Dialogfelder geöffnet oder einem Hauptrahmenfenster eigene, muss die Haupt-Meldungsverteilschleife der Anwendung eine Routine, die von der DLL, die ihrerseits exportierten Aufrufen der `CWinApp::PreTranslateMessage` Memberfunktion von der DLL-Application-Objekt.  

## <a name="mfc_optimization"></a> Welche Optimierungstechniken sollten verwendet werden zur Verbesserung der Clientanwendung&#39;s Leistung beim Laden?
Wenn die DLL eine reguläre MFC-DLL ist, die statisch mit MFC, ändern ihn in eine reguläre verknüpft ist reduziert MFC-DLL, die dynamisch mit MFC verknüpft wird die Dateigröße.  
  
 Wenn die DLL eine große Anzahl von exportierte Funktionen aufweist, verwenden Sie eine DEF-Datei zum Exportieren der Funktionen (anstatt **__declspec(dllexport)**) und verwenden Sie die DEF-Datei [NONAME-Attribut](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) auf jede exportierte Funktion. NONAME-Attribut bewirkt, dass nur den Ordinalwert und nicht der Funktionsname in der Exporttabelle der DLL gespeichert werden, wodurch die Dateigröße reduziert wird.  
  
 DLLs, die implizit mit einer Anwendung verknüpft werden geladen, wenn die Anwendung lädt. Versuchen Sie zur Verbesserung der Leistung beim Laden, unterteilen die DLL in verschiedenen DLLs aus. Alle Funktionen, die die aufrufende Anwendung unmittelbar nach dem Laden in eine DLL muss und die aufrufende Anwendung zunächst implizit mit dieser DLL verknüpft werden. Die anderen Funktionen, die nicht sofort die aufrufende Anwendung muss in eine andere DLL versetzt, und haben die Anwendung explizit mit dieser DLL verknüpfen. Weitere Informationen finden Sie unter [bestimmen welche Verknüpfungsmethode](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use).  

## <a name="memory_leak"></a> Es&#39;s eines Speicherverlusts in meiner reguläre MFC-DLL, aber die eigenen Code einwandfrei. Wie finde ich den Speicherverlust?  
  
Eine mögliche Ursache für den Speicherverlust ist, dass MFC temporäre Objekte erstellt, die innerhalb von Meldungshandlerfunktionen verwendet werden. In MFC-Anwendungen diese temporären Objekte werden automatisch bereinigt der `CWinApp::OnIdle()` Funktion, die zwischen der Verarbeitung von Nachrichten aufgerufen wird. Allerdings in MFC-Dynamic Link Libraries (DLLs) die `OnIdle()` Funktion wird nicht automatisch aufgerufen. Daher sind temporäre Objekte nicht automatisch bereinigt. Um temporäre Objekte zu bereinigen, die DLL explizit aufrufen muss `OnIdle(1)` in regelmäßigen Abständen.  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)