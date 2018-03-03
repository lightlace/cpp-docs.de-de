---
title: DLLs und Verhalten von Visual C++-Laufzeitbibliothek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75bf84eeaf9277c5cf037c4fa59c28d109d95856
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLLs und Verhalten von Visual C++-Laufzeitbibliothek  
  
Wenn Sie eine Dynamic Link Library (DLL) standardmäßig mithilfe von Visual C++ erstellen, enthält der Linker Visual C++-Laufzeitbibliothek (VCRuntime). Die VCRuntime enthält Code zum Initialisieren und beenden eine ausführbare C-/C++-Datei erforderlich. Wenn in einer DLL verknüpft wird, handelt es sich bei der VCRuntime-Code enthält eine interne DLL-Einstiegspunkt-Funktion wird aufgerufen, `_DllMainCRTStartup` , die Windows-Betriebssystem-Nachrichten an die DLL-Datei zum Anfügen oder trennen Sie einen Prozess oder Thread verarbeitet. Die `_DllMainCRTStartup` Funktion führt wichtige Aufgaben wie z. B. Stapel Puffer Sicherheit eingerichtet, C-Laufzeitbibliothek (CRT) initialisieren und beenden, und Aufrufe von Konstruktoren und Destruktoren für statische und globale Objekte. `_DllMainCRTStartup`auch Hookfunktionen Aufrufe anderen Bibliotheken wie WinRT MFC und ATL initialisieren und Beenden des eigenen ausführen. Ohne diese Initialisierung, CRT und anderen Bibliotheken, sowie Ihre statischen Variablen würden im nicht initialisierten Zustand bleiben. Die gleiche interne VCRuntime-Initialisierung und Beendigung Routinen heißen, ob die DLL statisch verknüpften CRT oder dynamisch verknüpfte CRT-DLL verwendet wird.  
  
## <a name="default-dll-entry-point-dllmaincrtstartup"></a>Standard-DLL Eintrag Punkt _DllMainCRTStartup  
  
In Windows können alle DLLs eine optionale Einstiegspunktfunktion, in der Regel enthalten `DllMain`, d. h. für Initialisierung und Terminierung aufgerufen. Dadurch haben Sie die Möglichkeit, zusätzliche Ressourcen je nach Bedarf zu reservieren oder freizugeben. Windows ruft die Einstiegspunktfunktion in den folgenden vier Situationen auf: Anfügen an bzw. Trennen von einem Prozess und Anfügen an einen bzw. Trennen von einem Thread. Wenn eine DLL-Datei in einen Prozessadressbereich geladen wird, beim Laden einer Anwendung, die verwendet werden, oder wenn die Anwendung die DLL zur Laufzeit anfordert, erstellt das Betriebssystem eine separate Kopie der DLL-Daten. Hierbei spricht *prozessanfügung*. *Fügen Sie den Thread* tritt auf, wenn der Prozess, der die DLL, in geladen wird einen neuen Thread erstellt. *Trennen von einem Thread* tritt auf, wenn der Thread beendet wird, und *prozesstrennung* ist, wenn die DLL nicht mehr erforderlich ist und wird von einer Anwendung freigegeben. Das Betriebssystem stellt einen separaten Aufruf von DLL-Einstiegspunkt für jedes dieser Ereignisse, und übergeben einer *Grund* Argument für jeden Ereignistyp. Das Betriebssystem sendet z. B. `DLL_PROCESS_ATTACH` als die *Grund* Argument signalisiert Prozess anfügen.  
  
Die VCRuntime-Bibliothek stellt eine Einstiegspunktfunktion aufgerufen `_DllMainCRTStartup` Standard Initialisierungs- und Terminierungscode Vorgänge behandelt. Prozess anfügen, die `_DllMainCRTStartup` Funktion Puffer-sicherheitsüberprüfungen richtet, initialisiert die CRT- und andere Bibliotheken, initialisiert die Laufzeit-Typeninformation, initialisiert und ruft Konstruktoren für statische und nicht lokale Daten, initialisiert den threadlokalen Speicher , erhöht einen interne statische Zähler für jede anfügen, und ruft anschließend die ein Benutzer oder Bibliothek-bereitgestellte `DllMain`. Trennen Sie den Prozess, die Funktion durchläuft in umgekehrter Reihenfolge Schritte. Sie ruft `DllMain`, verringert der interne Zähler ruft Destruktoren, Beendigung Aufrufe CRT-Funktionen und registriert `atexit` Funktionen und alle anderen Bibliotheken des Beendens benachrichtigt. Wenn der Anlage Zähler auf 0 (null) ist, gibt die Funktion `FALSE` Windows an, dass die DLL entladen werden kann. Die `_DllMainCRTStartup` Funktion wird auch während der Thread Anfügen und Trennen von einem Thread. In diesen Fällen die VCRuntime-Code führt eine zusätzliche Initialisierung oder Terminierung selbst und ruft nur `DllMain` zum Übergeben der Nachricht zusammen. Wenn `DllMain` gibt `FALSE` vom Prozess anfügen Signalisierung auftritt, `_DllMainCRTStartup` Aufrufe `DllMain` erneut aus und übergibt `DLL_PROCESS_DETACH` als die *Grund* Argument, durchläuft dann die restlichen der Beendigungsvorgangs.  
  
Beim Erstellen von DLLs in Visual C++ ist der Standardeinstiegspunkt `_DllMainCRTStartup` vom VCRuntime in automatisch verknüpft ist. Sie müssen nicht an eine Einstiegspunktfunktion für die DLL mit dem [/Entry (Einstiegspunktsymbol)](../build/reference/entry-entry-point-symbol.md) (Linkeroption).  
  
> [!NOTE]
> Es ist zwar möglich, eine andere Einstiegspunktfunktion für eine DLL-Datei angeben, indem Sie mit der/Entry: Linkeroption, nicht empfehlenswert, da die Einstiegspunktfunktion müsste alles duplizieren, `_DllMainCRTStartup` der Fall ist, in der gleichen Reihenfolge. Die VCRuntime bietet Funktionen, die Ihnen ermöglichen, ihr Verhalten zu duplizieren. Sie können z. B. Aufrufen [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) sofort auf den Prozess anfügen, zur Unterstützung der [/GS (Puffer-sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md) Puffer, die Option aktivieren, wird. Sie erreichen die `_CRT_INIT` -Funktion, die gleichen Parameter übergeben, als die Einstiegspunktfunktion, um den Rest der DLL-Initialisierung oder Terminierung Funktionen auszuführen.  
  
<a name="initializing-a-dll"></a>  
  
## <a name="initialize-a-dll"></a>Initialisieren einer DLL  
  
Die DLL möglicherweise Initialisierungscode, die beim Laden der DLL ausgeführt werden muss. In der Reihenfolge Sie Ihre eigenen DLL Initialisierungs- und Terminierungscode Funktionen ausführen `_DllMainCRTStartup` Ruft eine Funktion namens `DllMain` , die Sie bereitstellen können. Ihre `DllMain` benötigen die Signatur für eine DLL-Einstiegspunkt erforderlich sind. Der Standard-Einstiegspunktfunktion `_DllMainCRTStartup` Aufrufe `DllMain` mit denselben Parametern übergeben von Windows. Standardmäßig, wenn Sie keine ergeben eine `DllMain` -Funktion, Visual C++ bietet für Sie und verknüpft es im, damit `_DllMainCRTStartup` verfügt immer über eine Funktion aufrufen. Dies bedeutet, dass wenn Sie nicht die DLL jedoch initialisiert werden müssen, keine besonderen Sie müssen lediglich beim Erstellen der DLL sind.  
  
Dies ist die Signatur für `DllMain`:  
  
```cpp  
#include <windows.h>  
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```  
  
Einige Bibliotheken umschließen die `DllMain` -Funktion für Sie. In einer regulären MFC-DLL, z. B. Implementieren der `CWinApp` des Objekts `InitInstance` und `ExitInstance` Memberfunktionen zur Durchführung von Initialisierungs- und Terminierungscode für die DLL erforderlich. Weitere Informationen finden Sie unter der [reguläre MFC-DLLs initialisieren](#initializing-regular-dlls) Abschnitt.  
  
> [!WARNING]
> Auf problemlos in eine DLL-Einstiegspunkt Verwendungsmöglichkeiten sind wichtige Einschränkungen. Finden Sie unter [allgemein empfohlene Vorgehensweisen](https://msdn.microsoft.com/library/windows/desktop/dn633971#general_best_practices) bestimmter Windows-APIs, die in Aufrufen unsicher sind `DllMain`. Wenn Sie einen müssen klicken Sie dann die einfachste Initialisierung sollten, die in einer Initialisierungsfunktion für die DLL. Sie können anfordern, dass die Initialisierungsfunktion nach aufrufen, `DllMain` wurde ausgeführt wurde und bevor sie andere Funktionen in die DLL aufrufen.  
  
<a name="initializing-non-mfc-dlls"></a>  
  
### <a name="initialize-ordinary-non-mfc-dlls"></a>Normale (MFC-Fremd)-DLLs initialisieren  
  
Für die eigene Initialisierung in normalen (MFC-Fremd) DLLs, die die VCRuntime bereitgestellte verwenden `_DllMainCRTStartup` Einstiegspunkt, muss der DLL-Quellcode eine Funktion mit dem Namen enthalten `DllMain`. Der folgende Code zeigt eine grundlegende Skeleton angezeigt wie die Definition von `DllMain` kann folgendermaßen aussehen:  
  
```cpp  
#include <windows.h>
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason) 
    { 
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```  
  
> [!NOTE]
> Ältere Windows-SDK-Dokumentation besagt, dass der tatsächliche Name der DLL-Einstiegspunkt-Funktion auf der Befehlszeile mit der Option/Entry Linker angegeben werden muss. Mit Visual C++, Sie müssen nicht die/Entry-Option verwenden, wenn die Einstiegspunktfunktion heißt `DllMain`. Tatsächlich bei Verwendung der Option/Entry und der Name der Einstiegspunkt funktioniert etwas anders als `DllMain`, CRT ist nicht ordnungsgemäß initialisiert abrufen, es sei denn, die Einstiegspunktfunktion die Aufrufe der gleichen Initialisierung, besteht `_DllMainCRTStartup` macht.  
  
<a name="initializing-regular-dlls"></a>  
  
### <a name="initialize-regular-mfc-dlls"></a>Reguläre MFC-DLLs initialisieren  
  
Da reguläre MFC-DLLs haben eine `CWinApp` -Objekt, sollten sie ihre initialisieren und Beenden des Tasks ausführen, am gleichen Speicherort wie eine MFC-Anwendung: in der `InitInstance` und `ExitInstance` Memberfunktionen der DLL `CWinApp`-abgeleitet -Klasse. Da MFC bietet ein `DllMain` Funktion, die aufgerufen wird, indem Sie `_DllMainCRTStartup` für `DLL_PROCESS_ATTACH` und `DLL_PROCESS_DETACH`, sollten Sie keinen eigenen `DllMain` Funktion. Die MFC bereitgestellten `DllMain` Funktionsaufrufe `InitInstance` beim Laden der DLL, und es ruft `ExitInstance` , bevor die DLL entladen wird.  
  
Eine reguläre MFC-DLL kann von mehreren Threads durch verfolgt Aufrufen [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) und [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812) in seiner `InitInstance` Funktion. Mit diesen Funktionen kann die DLL für threadspezifische Daten verfolgen.  
  
In der regulären MFC-DLL, die dynamisch mit MFC, verknüpft Wenn Sie sind mit einem beliebigen MFC OLE, MFC-Datenbank (oder DAO) oder MFC-Sockets, bzw. unterstützen die Debug-MFC-Erweiterungs-DLLs MFCO*Version*D.dll, MFCD*Version*D.dll und MFCN*Version*D.dll (wobei *Version* ist die Versionsnummer) automatisch verknüpft sind. Müssen Sie eine der folgenden vordefinierten Initialisierungsfunktionen für jede dieser DLLs, die Sie in der regulären MFC DLL verwenden Aufrufen `CWinApp::InitInstance`.  
  
|Art der MFC-Unterstützung|Die Initialisierungsfunktion aufrufen|  
|-------------------------|-------------------------------------|  
|MFC-OLE (MFCO*Version*D.dll)|`AfxOleInitModule`|  
|MFC-Datenbank (MFCD*Version*D.dll)|`AfxDbInitModule`|  
|MFC-Sockets (MFCN*Version*D.dll)|`AfxNetInitModule`|  
  
<a name="initializing-extension-dlls"></a>  
  
### <a name="initialize-mfc-extension-dlls"></a>MFC-Erweiterungs-DLLs initialisieren  
  
Da MFC-Erweiterungs-DLLs keine `CWinApp`-abgeleitete Objekt (wie reguläre MFC-DLLs), sollten Sie die Initialisierungs- und Terminierungscode Code zum Hinzufügen der `DllMain` Funktion, die vom MFC-DLL-Assistenten generiert.  
  
 Für MFC-Erweiterungs-DLLs, bietet der Assistent den folgenden Code. Im Code `PROJNAME` ist ein Platzhalter für den Namen des Projekts.  
  
```cpp  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // MFC extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
Erstellen eines neuen `CDynLinkLibrary` Objekts während der Initialisierung können MFC-Erweiterungs-DLL-Datei exportieren `CRuntimeClass` Objekte oder-Ressourcen von der Clientanwendung.  
  
Wenn Sie die MFC-Erweiterungs-DLL von ein oder mehrere reguläre MFC-DLLs verwenden möchten, müssen Sie eine Initialisierungsfunktion, die erstellt Exportieren einer `CDynLinkLibrary` Objekt. Diese Funktion muss von jedem der regulären MFC-DLLs aufgerufen werden, die MFC-Erweiterungs-DLL zu verwenden. Befindet sich in eine geeignete Stelle zum Aufrufen dieser Initialisierungsfunktion der `InitInstance` Memberfunktion von den regulären MFC DLL `CWinApp`-abgeleitetes Objekt vor der Verwendung der MFC-Erweiterungs-DLL exportierten Klassen oder Funktionen.  
  
In der `DllMain` , dass die MFC-DLL-Assistenten generiert, den Aufruf von `AfxInitExtensionModule` erfasst das Modul zur Laufzeit-Klassen (`CRuntimeClass` Strukturen) sowie die Objektfactory (`COleObjectFactory` Objekte) für die Verwendung der `CDynLinkLibrary` Objekt wird erstellt. Sie sollten überprüfen, den Rückgabewert des `AfxInitExtensionModule`; Wenn ein NULL-Wert zurückgegeben wird, aus `AfxInitExtensionModule`, Zurückgeben von 0 (null), aus der `DllMain` Funktion.  
  
Wenn die MFC-Erweiterungs-DLL in eine ausführbare Datei explizit verknüpft wird (d. h. die ausführbare Datei ruft `AfxLoadLibrary` zum Verknüpfen der DLL), sollten Sie einen Aufruf von hinzufügen `AfxTermExtensionModule` auf `DLL_PROCESS_DETACH`. Diese Funktion ermöglicht es MFC ermöglicht, bereinigen Sie die MFC-Erweiterungs-DLL, wenn jeder Prozess von der MFC-Erweiterungs-DLL trennt (das geschieht, wenn der Prozess beendet wird oder wenn die DLL, als Ergebnis des entladen wird eine `AfxFreeLibrary` aufrufen). Wenn die MFC-Erweiterungs-DLL implizit soll, an die Anwendung, die den Aufruf von verknüpft werden `AfxTermExtensionModule` ist nicht erforderlich.  
  
Anwendungen, die Verknüpfung mit MFC-Erweiterungs-DLLs explizit aufrufen, muss `AfxTermExtensionModule` , wenn die DLL freigeben. Sie sollten auch verwenden, `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle der Win32-Funktionen `LoadLibrary` und `FreeLibrary`) Wenn die Anwendung mehrere Threads verwendet. Mit `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass das Starten und Herunterfahren Code, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL wird geladen und entladen, die nicht über den Status der globalen MFC beschädigt.  
  
Da MFCx0.dll Zeitpunkt vollständig initialisiert wurde `DllMain` wird aufgerufen, können Sie Speicher und MFC-Funktionen in Aufrufen `DllMain` (im Gegensatz zu den 16-Bit-Version von MFC).  
  
Erweiterungs-DLLs kümmern multithreading durch Behandeln der `DLL_THREAD_ATTACH` und `DLL_THREAD_DETACH` in Fällen die `DllMain` Funktion. Diese Fälle werden zum übergeben `DllMain` Wenn Threads Anfügen und trennen Sie die DLL. Aufrufen von [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) beim Anfügen an eine DLL ist, kann die DLL für Threads Verwalten lokaler Speicher (TLS) für jeden Thread, der an die DLL angefügt indiziert.  
  
Beachten Sie, dass die Headerdatei "afxdllx.h" spezielle Definitionen für Strukturen, die in MFC-Erweiterungs-DLLs, z. B. die Definition für verwendeten enthält `AFX_EXTENSION_MODULE` und `CDynLinkLibrary`. Sie sollten diese Headerdatei in der MFC-Erweiterungs-DLL aufnehmen.  
  
> [!NOTE]
>  Es ist wichtig, dass Sie weder definieren noch keines der `_AFX_NO_XXX` Makros in "stdafx.h". Diese Makros sind nur, um zu überprüfen, ob eine bestimmte Zielplattform dieses Feature oder nicht unterstützt vorhanden. Sie können das Programm überprüft diese Makros schreiben (z. B. `#ifndef _AFX_NO_OLE_SUPPORT`), aber Ihr Programm sollte nie definieren oder diese Makros aufzuheben.  
  
Eine Beispiel-Initialisierung-Funktion, die multithreading behandelt dient in [Using Thread Local Storage in einer Dynamic Link Library](http://msdn.microsoft.com/library/windows/desktop/ms686997) im Windows SDK. Beachten Sie, dass das Beispiel eine Einstiegspunktfunktion aufgerufen enthält `LibMain`, aber Sie sollten diese Funktion benennen `DllMain` so, dass sie mit der MFC und C-Laufzeitbibliotheken funktioniert.  
  
## <a name="see-also"></a>Siehe auch  
  
[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)  
[DllMain-Einstiegspunkt](https://msdn.microsoft.com/library/windows/desktop/ms682583.aspx)  
[Dynamic Link Library, bewährte Methoden](https://msdn.microsoft.com/library/windows/desktop/dn633971.aspx)  