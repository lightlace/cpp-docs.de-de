---
title: DLLs und Verhalten C++ der visuellen Lauf Zeit Bibliothek
ms.date: 05/06/2019
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
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
ms.openlocfilehash: d44f3bf7a8b06f567b1af221e17085d589e56aca
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492618"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLLs und Verhalten C++ der visuellen Lauf Zeit Bibliothek

Wenn Sie eine Dynamic Link Library (dll) mithilfe von Visual Studio erstellen, enthält der Linker standardmäßig die visuelle C++ Lauf Zeit Bibliothek (vcruntime). Die vcruntime enthält den Code, der zum Initialisieren und Beenden einerC++ C/ausführbaren Datei erforderlich ist. Beim Verknüpfen mit einer dll stellt der vcruntime-Code eine interne DLL-Einstiegspunkt Funktion `_DllMainCRTStartup` bereit, die Windows-Betriebssystem Meldungen an die dll verarbeitet, die an einen Prozess oder Thread angefügt oder von diesem getrennt werden sollen. Die `_DllMainCRTStartup` -Funktion führt wichtige Aufgaben aus, z. b. das Einrichten von Stapelpuffer Sicherheit, die Initialisierung der C-Lauf Zeit Bibliothek (CRT) und die Beendigung sowie Aufrufe von Konstruktoren und Debuggern für statische und globale Objekte. `_DllMainCRTStartup`Ruft auch Hook-Funktionen für andere Bibliotheken wie WinRT, MFC und ATL auf, um eine eigene Initialisierung und Beendigung auszuführen. Ohne diese Initialisierung würden die CRT und andere Bibliotheken sowie die statischen Variablen in einem nicht initialisierten Zustand verbleiben. Die gleichen vcruntime-internen Initialisierungs-und Beendigungs Routinen werden aufgerufen, unabhängig davon, ob Ihre DLL eine statisch verknüpfte CRT oder eine dynamisch verknüpfte CRT-DLL verwendet.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>Standard-DLL-Einstiegspunkt _DllMainCRTStartup

In Windows können alle DLLs eine optionale Einstiegspunkt Funktion enthalten, die in der Regel `DllMain`als bezeichnet wird und für Initialisierung und Beendigung aufgerufen wird. Dadurch haben Sie die Möglichkeit, zusätzliche Ressourcen je nach Bedarf zu reservieren oder freizugeben. Windows ruft die Einstiegspunktfunktion in den folgenden vier Situationen auf: Anfügen an bzw. Trennen von einem Prozess und Anfügen an einen bzw. Trennen von einem Thread. Wenn eine DLL in einen Prozess Adressraum geladen wird, entweder wenn eine Anwendung, die Sie verwendet, geladen wird, oder wenn die Anwendung die dll zur Laufzeit anfordert, erstellt das Betriebssystem eine separate Kopie der DLL-Daten. Dies wird als *Prozess anfügen*bezeichnet. *Thread anfügen* tritt auf, wenn der Prozess, in den die dll geladen wird, einen neuen Thread erstellt. *Thread* Trennung tritt auf, wenn der Thread beendet wird, und der *Prozess trennt* , wenn die dll nicht mehr benötigt wird und von einer Anwendung freigegeben wird. Das Betriebssystem führt einen separaten Rückruf für den DLL-Einstiegspunkt für jedes dieser Ereignisse aus und übergibt ein Argument für jeden Ereignistyp. Das Betriebssystem sendet `DLL_PROCESS_ATTACH` z. b. als Argument Argument, um das Anfügen von Prozessen zu signalisieren.

Die vcruntime-Bibliothek bietet eine Einstiegspunkt Funktion, `_DllMainCRTStartup` die aufgerufen wird, um standardmäßige Initialisierungs-und Beendigungs Vorgänge zu verarbeiten. Beim Anfügen des Prozesses `_DllMainCRTStartup` richtet die Funktion Puffer Sicherheitsüberprüfungen ein, initialisiert die CRT und andere Bibliotheken, initialisiert Lauf Zeittyp Informationen, initialisiert und ruft Konstruktoren für statische und nicht lokale Daten auf, initialisiert den Thread lokalen Speicher. , Inkremente einen internen statischen Zählers für jede Anfügung und dann einen von einem Benutzer oder einer `DllMain`Bibliothek bereitgestellten. Beim Prozess trennen durchläuft die Funktion diese Schritte in umgekehrter Reihenfolge. Sie ruft `DllMain`auf, Dekremente den internen-Wert, ruft Dekonstruktoren auf, ruft CRT `atexit` -Beendigungs Funktionen und registrierte Funktionen auf und benachrichtigt alle anderen Bibliotheken der Beendigung. Wenn der Anlagen Indikator null wechselt, gibt die Funktion zurück `FALSE` , um Windows anzuzeigen, dass die DLL entladen werden kann. Die `_DllMainCRTStartup` -Funktion wird auch beim Anfügen und trennen von Threads aufgerufen. In diesen Fällen führt der vcruntime-Code weder eine zusätzliche Initialisierung noch eine Beendigung aus, und es wird `DllMain` lediglich aufgerufen, um die Nachricht zu übergeben. Wenn `DllMain` von `FALSE` der Prozess Anfügung zurückgibt, `_DllMainCRTStartup` das Signal fehlschlägt `DLL_PROCESS_DETACH` , erneut aufruft `DllMain` und als *reason* -Argument übergibt, durchläuft den Rest des Beendigungs Vorgangs.

Beim Aufbau von DLLs in Visual Studio wird der von vcruntime angegebene Standard Einstiegspunkt `_DllMainCRTStartup` automatisch verknüpft. Sie müssen keine Einstiegspunkt Funktion für die DLL angeben, indem Sie die Linkeroption [/Entry (Einstiegspunkt Symbol)](reference/entry-entry-point-symbol.md) verwenden.

> [!NOTE]
> Obwohl es möglich ist, eine andere Einstiegspunkt Funktion für eine DLL mithilfe der/Entry: Linker-Option anzugeben, wird Sie nicht empfohlen, da die Einstiegspunkt Funktion alle Elemente in derselben Reihenfolge duplizieren `_DllMainCRTStartup` muss. Die vcruntime stellt Funktionen bereit, die es Ihnen ermöglichen, das Verhalten zu duplizieren. Sie können z. b. [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) sofort für den Prozess anfügen, um die Puffer Überprüfungs Option [/GS (Buffer Security Check)](reference/gs-buffer-security-check.md) zu unterstützen. Sie können die `_CRT_INIT` -Funktion aufzurufen und die gleichen Parameter wie die Einstiegspunkt Funktion übergeben, um die restlichen Funktionen der DLL-Initialisierung oder-Beendigung auszuführen.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>Initialisieren einer DLL

Die dll verfügt möglicherweise über Initialisierungs Code, der beim Laden der DLL ausgeführt werden muss. Damit Sie Ihre eigenen dll-Initialisierungs-und Beendigungs Funktionen ausführen können `_DllMainCRTStartup` , ruft eine Funktion `DllMain` mit dem Namen auf, die Sie bereitstellen können. Ihr `DllMain` muss über die erforderliche Signatur für einen DLL-Einstiegspunkt verfügen. Die Standard-Einstiegspunkt `_DllMainCRTStartup` Funktion `DllMain` Ruft mit denselben Parametern auf, die von Windows übermittelt werden. Wenn Sie keine `DllMain` Funktion bereitstellen, stellt Visual Studio standardmäßig einen für Sie bereit und verknüpft ihn darin, `_DllMainCRTStartup` damit immer etwas aufgerufen werden kann. Dies bedeutet Folgendes: Wenn Sie die dll nicht initialisieren müssen, müssen Sie bei der Erstellung der dll nichts Besonderes tun.

Dies ist die Signatur, die `DllMain`für Folgendes verwendet wird:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Einige Bibliotheken schließen die `DllMain` Funktion für Sie ein. Implementieren Sie z. b. in einer regulären MFC- `CWinApp` dll die `InitInstance` - `ExitInstance` und-Member-Funktionen des-Objekts, um für die dll erforderliche Initialisierung und Beendigung auszuführen. Weitere Informationen finden Sie im Abschnitt [Initialisieren regulärer MFC-DLLs](#initializing-regular-dlls) .

> [!WARNING]
> Es gibt erhebliche Beschränkungen hinsichtlich der Sicherheit eines dll-Einstiegs Punkts. Weitere Informationen finden Sie unter [allgemeine bewährte Methoden](/windows/win32/Dlls/dynamic-link-library-best-practices) für bestimmte Windows-APIs, `DllMain`die nicht für den aufzurufenden Wenn Sie etwas außer der einfachsten Initialisierung benötigen, führen Sie dies in einer Initialisierungsfunktion für die dll aus. Sie können erfordern, dass Anwendungen die Initialisierungsfunktion aufruft `DllMain` , nachdem ausgeführt wurde und bevor Sie andere Funktionen in der DLL aufruft.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Initialisieren von normalen DLLs (nicht-MFC)

Um Ihre eigene Initialisierung in normalen (nicht-MFC-DLLs) auszuführen, die den von vcruntime `_DllMainCRTStartup` angegebenen Einstiegspunkt verwenden, muss der DLL-Quellcode eine Funktion `DllMain`mit dem Namen enthalten. Der folgende Code zeigt ein einfaches Gerüst, das zeigt, wie `DllMain` die Definition von aussehen könnte:

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
> Ältere Windows SDK Dokumentation besagt, dass der tatsächliche Name der DLL-Einstiegspunkt Funktion in der Linker-Befehlszeile mit der/Entry-Option angegeben werden muss. In Visual Studio müssen Sie die Option/Entry nicht verwenden, wenn der Name der Einstiegspunkt Funktion ist `DllMain`. Tatsächlich wird die CRT nicht ordnungsgemäß initialisiert, wenn Sie die/Entry-Option verwenden und die `DllMain`Einstiegspunkt Funktion mit einem anderen Namen als benennen, es sei denn, die Einstiegspunkt Funktion führt dieselben Initialisierungs `_DllMainCRTStartup` Aufrufe aus, die von ausgeführt werden.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Reguläre MFC-DLLs initialisieren

Da reguläre MFC-DLLs über `CWinApp` ein `CWinApp`-Objekt verfügen, sollten Sie die Initialisierungs-und Beendigungs Aufgaben am gleichen Speicherort wie eine MFC `InitInstance` - `ExitInstance` Anwendung ausführen: in den-und-Member-Funktionen der von der dll abgeleiteten klassi. Da `DllMain` MFC eine Funktion bereitstellt, die von `_DllMainCRTStartup` für `DLL_PROCESS_ATTACH` und `DLL_PROCESS_DETACH`aufgerufen wird, sollten Sie keine eigene `DllMain` Funktion schreiben. Die von MFC bereit `DllMain` gestellte Funktion `InitInstance` Ruft auf, wenn die dll geladen wird `ExitInstance` , und ruft auf, bevor die DLL entladen wird.

Eine reguläre MFC-DLL kann mehrere Threads nachverfolgen, indem Sie [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) und [TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) in `InitInstance` der Funktion aufrufen. Diese Funktionen ermöglichen es der dll, Thread spezifische Daten zu verfolgen.

In ihrer regulären MFC-DLL, die dynamisch mit MFC verknüpft ist, wenn Sie eine MFC-OLE-, MFC-Datenbank-(oder DAO-) oder MFC-Socketunterstützung verwenden, sind die Debug-MFC-Erweiterungs-DLLs mfco*Version*d. dll, MFCD*Version*d. dll und mfcn*Version*d. dll ( Wenn *Version* die Versionsnummer ist, werden Sie automatisch verknüpft. Sie müssen eine der folgenden vordefinierten Initialisierungs Funktionen für jede dieser DLLs aufzurufen, die Sie in ihren regulären MFC-DLL-Assemblys `CWinApp::InitInstance`verwenden.

|MFC-Unterstützung|Aufzurufende Initialisierungsfunktion|
|-------------------------|-------------------------------------|
|MFC-OLE (mfco*Version*D. dll)|`AfxOleInitModule`|
|MFC-Datenbank (MFCD*Version*D. dll)|`AfxDbInitModule`|
|MFC-Sockets (mfcn*Version*D. dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC-Erweiterungs-DLLs initialisieren

Da MFC `CWinApp`-Erweiterungs-DLLs über kein von abgeleitetes Objekt verfügen (wie reguläre MFC-DLLs), sollten Sie den Initialisierungs-und Beendigungs Code der `DllMain` Funktion hinzufügen, die vom MFC-DLL-Assistenten generiert wird.

Der Assistent stellt den folgenden Code für MFC-Erweiterungs-DLLs bereit. Im Code `PROJNAME` ist ein Platzhalter für den Namen des Projekts.

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

Das Erstellen eines `CDynLinkLibrary` neuen Objekts während der Initialisierung ermöglicht der MFC-Erweiterungs `CRuntimeClass` -dll das Exportieren von Objekten oder Ressourcen in die Client Anwendung.

Wenn Sie die MFC-Erweiterungs-DLL aus einer oder mehreren regulären MFC-DLLs verwenden möchten, müssen Sie eine Initialisierungsfunktion exportieren, die `CDynLinkLibrary` ein-Objekt erstellt. Diese Funktion muss von allen regulären MFC-DLLs aufgerufen werden, die die MFC-Erweiterungs-DLL verwenden. Eine geeignete Stelle zum Abrufen dieser Initialisierungsfunktion ist in der `InitInstance` Member `CWinApp`-Funktion des von abgeleiteten MFC-DLL-Objekts, bevor eine der exportierten Klassen oder Funktionen der MFC-Erweiterungs-DLL verwendet wird.

In der `DllMain` , die der MFC-DLL-Assistent generiert, `AfxInitExtensionModule` erfasst der Aufruf von die Lauf Zeit Klassen (`CRuntimeClass` Strukturen) des Moduls sowie die zugehörigen objektfactorys (`COleObjectFactory` -Objekte `CDynLinkLibrary` ), die beim Erstellen des Objekts verwendet werden sollen. Sie sollten den Rückgabewert von `AfxInitExtensionModule`überprüfen. wenn der Wert 0 (null) von `AfxInitExtensionModule`zurückgegeben wird `DllMain` , wird von der Funktion NULL zurückgegeben.

Wenn Ihre MFC-Erweiterungs-DLL explizit mit einer ausführbaren Datei verknüpft wird (d `AfxLoadLibrary` . h. die ausführbaren Aufrufe zum Verknüpfen mit der dll) `AfxTermExtensionModule` , `DLL_PROCESS_DETACH`sollten Sie einen Aufruf von auf hinzufügen. Diese Funktion ermöglicht MFC das Bereinigen der MFC-Erweiterungs-DLL, wenn jeder Prozess von der MFC-Erweiterungs-DLL trennt (was geschieht, wenn der Prozess beendet wird oder wenn die dll als `AfxFreeLibrary` Ergebnis eines-Aufrufes entladen wird). Wenn Ihre MFC-Erweiterungs-DLL implizit mit der Anwendung verknüpft wird, `AfxTermExtensionModule` ist der-Vorgang nicht erforderlich.

Anwendungen, die explizit mit MFC-Erweiterungs-DLLs `AfxTermExtensionModule` verknüpfen, müssen beim Freigeben der dll aufgerufen werden. Sie sollten außerdem und `AfxLoadLibrary` `AfxFreeLibrary` (anstelle der Win32-Funktionen `LoadLibrary` und `FreeLibrary`) verwenden, wenn die Anwendung mehrere Threads verwendet. Durch `AfxLoadLibrary` die `AfxFreeLibrary` Verwendung von und wird sichergestellt, dass beim Laden und Entladen der MFC-Erweiterungs-DLL der globale MFC-Status durch das Starten und Herunterfahren des Codes beschädigt wird.

Da die Datei MFCx0. dll vollständig initialisiert ist, `DllMain` wenn aufgerufen wird, können Sie Arbeitsspeicher zuweisen und MFC- `DllMain` Funktionen in aufrufen (im Gegensatz zur 16-Bit-Version von MFC).

Erweiterungs-DLLs können das Multithreading behandeln, indem Sie `DLL_THREAD_ATTACH` die `DLL_THREAD_DETACH` -und- `DllMain` Fälle in der-Funktion verarbeiten. Diese Fälle werden an den `DllMain` , wenn Threads an die dll anfügen und trennen. Wenn Sie [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) aufrufen, wenn eine DLL angefügt wird, kann die dll lokale TLS-Indizes (Thread Local Storage) für jeden an die dll angefügten Thread verwalten.

Beachten Sie, dass die Header Datei Afxdllx. h spezielle Definitionen für Strukturen enthält, die in MFC-Erweiterungs-DLLs verwendet `AFX_EXTENSION_MODULE` werden `CDynLinkLibrary`, z. b. die Definition für und. Sie sollten diese Header Datei in der MFC-Erweiterungs-DLL einschließen.

> [!NOTE]
>  Es ist wichtig, dass Sie keines der `_AFX_NO_XXX` Makros in stdafx. h definieren und nicht definieren. Diese Makros sind nur zum Zweck der Überprüfung vorhanden, ob eine bestimmte Zielplattform diese Funktion unterstützt. Sie können Ihr Programm schreiben, um diese Makros zu überprüfen ( `#ifndef _AFX_NO_OLE_SUPPORT`z. b.), aber Ihr Programm sollte diese Makros nie definieren bzw. nicht definieren.

Eine Beispiel Initialisierungsfunktion, die Multithreading behandelt, ist in die [Verwendung von lokalem Thread Speicher in einer Dynamic Link Library](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) im Windows SDK eingeschlossen. Beachten Sie, dass das Beispiel eine Einstiegspunkt Funktion `LibMain`mit dem Namen enthält. Sie sollten diese Funktion `DllMain` jedoch benennen, damit Sie mit den MFC-und C-Laufzeitbibliotheken funktioniert.

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)<br/>
[DllMain-Einstiegspunkt](/windows/win32/Dlls/dllmain)<br/>
[Bewährte Methoden für die Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-best-practices)
