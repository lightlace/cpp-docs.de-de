---
title: DLLs und Verhalten von Visual C++-Laufzeitbibliothek
ms.date: 11/04/2016
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
ms.openlocfilehash: 8293e2e05193b34802aba0af722dd06155fdcd81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429054"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLLs und Verhalten von Visual C++-Laufzeitbibliothek

Wenn Sie einer Dynamic Link Library (DLL) werden standardmäßig mithilfe von Visual C++ erstellen, enthält der Linker die Visual C++-Laufzeitbibliothek (VCRuntime). Die VCRuntime enthält Code zum Initialisieren und beenden eine C/C++-exe-Datei. Wenn in einer DLL verknüpft wird, handelt es sich bei der VCRuntime-Code enthält eine interne DLL-Einstiegspunkt-Funktion wird aufgerufen, `_DllMainCRTStartup` , die Windows-Betriebssystem-Nachrichten an die DLL an anfügen oder trennen Sie einen Prozess oder Thread verarbeitet. Die `_DllMainCRTStartup` Funktion führt wichtige Aufgaben wie das Stack-Puffer-Sicherheit eingerichtet, C-Laufzeitbibliothek (CRT)-Initialisierung und Beendigung und Aufrufe an die Konstruktoren und Destruktoren für statische und globale Objekte. `_DllMainCRTStartup` auch Hookfunktionen Aufrufe für andere Bibliotheken wie z. B. WinRT, MFC- und ATL-eigene Initialisierung und Beendigung ausführen. Ohne diese Initialisierung, der CRT und anderen Bibliotheken, sowie die statische Variablen würde in einem nicht initialisierten Zustand verbleiben. Die gleichen internen VCRuntime-Initialisierung und Beendigung Routinen heißen, ob die DLL einer statisch verknüpften CRT oder einen dynamisch verknüpfte CRT-DLL verwendet wird.

## <a name="default-dll-entry-point-dllmaincrtstartup"></a>Standard-DLL Eintrag Punkt _DllMainCRTStartup

In Windows, können alle DLLs eine optionale Einstiegspunktfunktion, in der Regel dem Namen enthalten `DllMain`, d. h. für Initialisierung und Beendigung aufgerufen. Dadurch haben Sie die Möglichkeit, zusätzliche Ressourcen je nach Bedarf zu reservieren oder freizugeben. Windows ruft die Einstiegspunktfunktion in den folgenden vier Situationen auf: Anfügen an bzw. Trennen von einem Prozess und Anfügen an einen bzw. Trennen von einem Thread. Wenn eine DLL-Datei in einen Prozessadressbereich, geladen wird, wenn eine Anwendung, die es verwendet, geladen wird oder wenn die Anwendung die DLL zur Laufzeit anfordert, erstellt das Betriebssystem eine separate Kopie der DLL-Daten. Dies wird als bezeichnet *prozessanfügung*. *Fügen Sie den Thread* tritt auf, wenn der Prozess, der die DLL, in geladen wird einen neuen Thread erstellt. *Trennen von einem Thread* tritt auf, wenn der Thread beendet wird, und *prozesstrennung* ist, wenn die DLL nicht mehr erforderlich ist und wird von einer Anwendung freigegeben. Das Betriebssystem stellt einen separaten Aufruf von DLL-Einstiegspunkts für jedes dieser Ereignisse, und übergeben einen *Grund* Argument für jeden Ereignistyp. Das Betriebssystem sendet beispielsweise `DLL_PROCESS_ATTACH` als die *Grund* anfügen Argument für den Prozess zu signalisieren.

Die VCRuntime-Bibliothek stellt eine Einstiegspunktfunktion namens `_DllMainCRTStartup` Standardvorgänge Initialisierungs- und Terminierungscode behandelt. Prozess anfügen, die `_DllMainCRTStartup` Funktion Puffer-sicherheitsüberprüfungen richtet, initialisiert die CRT und andere Bibliotheken, initialisiert die Laufzeit Typinformationen, initialisiert und ruft Konstruktoren für statische und nicht lokale Daten, initialisiert threadlokaler Speicher , erhöht einen interne statische Zähler für jede Anfügen und ruft dann ein Benutzer oder Bibliothek-bereitgestellten `DllMain`. Prozess trennen, die Funktion durchläuft diese Schritte in umgekehrter Reihenfolge. Ruft `DllMain`, verringert der interne Indikator, der Destruktor aufgerufen, und Aufrufe CRT Beendigung Funktionen registriert `atexit` Funktionen und alle anderen Bibliotheken der Beendigung benachrichtigt. Die Funktion gibt zurück, wenn die Anlage Zähler auf NULL zurückgeht, `FALSE` Windows an, dass die DLL entladen werden kann. Die `_DllMainCRTStartup` Funktion wird auch aufgerufen, während der Thread Anfügen und Trennen von einem Thread. In diesen Fällen die VCRuntime-Code ist zusätzliche Initialisierung oder Terminierung selbst und ruft nur `DllMain` zum Übergeben der Nachricht an. Wenn `DllMain` gibt `FALSE` vom Prozess anfügen signalisiert Fehler auftritt, `_DllMainCRTStartup` Aufrufe `DllMain` wieder und übergibt `DLL_PROCESS_DETACH` als die *Grund* -Argument, durchläuft dann die restlichen der verbindungsbeendigungs-Prozess.

Beim Erstellen von DLLs in Visual C++ den Standardeinstiegspunkt `_DllMainCRTStartup` vom VCRuntime in automatisch verknüpft ist. Sie müssen sich nicht an eine Einstiegspunktfunktion für Ihre DLL-Datei mithilfe der [/Entry (Einstiegspunktsymbol)](../build/reference/entry-entry-point-symbol.md) -Linkeroption.

> [!NOTE]
> Es ist zwar möglich, eine andere Einstiegspunktfunktion für eine DLL zu angeben, indem Sie den/Entry:-Linkeroption, es wird nicht empfohlen, da die Einstiegspunktfunktion müssten alle, `_DllMainCRTStartup` der Fall ist, in der gleichen Reihenfolge. Die VCRuntime bietet Funktionen, die Ihnen ermöglichen, die dessen Verhalten zu reproduzieren. Sie können z. B. Aufrufen ["__security_init_cookie"](../c-runtime-library/reference/security-init-cookie.md) sofort auf den Prozess anfügen, zur Unterstützung der [/GS (Puffer-sicherheitsüberprüfung)](../build/reference/gs-buffer-security-check.md) Puffer, die Option aktivieren, wird. Rufen Sie die `_CRT_INIT` Funktion auf und übergibt die gleichen Parameter wie die Einstiegspunktfunktion, um den Rest der DLL-Initialisierung oder Terminierung Funktionen auszuführen.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>Initialisieren einer DLL

Die DLL möglicherweise Initialisierungscode, die beim Laden der DLL ausgeführt werden muss. In der Reihenfolge für Sie Ihren eigenen DLL Initialisierungs- und Terminierungscode Funktionen `_DllMainCRTStartup` Ruft eine Funktion namens `DllMain` , die Sie bereitstellen können. Ihre `DllMain` müssen die Signatur für eine DLL-Einstiegspunkt erforderlich sind. Die Standard-Einstiegspunktfunktion `_DllMainCRTStartup` Aufrufe `DllMain` mit denselben Parametern übergeben von Windows. Standardmäßig, wenn Sie keinen angeben einer `DllMain` -Funktion, Visual C++ stellt für Sie und verknüpft es im, damit `_DllMainCRTStartup` verfügt immer über eine Funktion aufrufen. Dies bedeutet, dass wenn Sie nicht benötigen, um die DLL jedoch initialisiert werden, keine besonderen man dazu Unternehmen muss beim Erstellen der DLL sind.

Dies ist die Signatur, die zum `DllMain`:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Einige Bibliotheken umschließen der `DllMain` -Funktion für Sie. In einer regulären MFC-DLL, z. B. Implementieren der `CWinApp` des Objekts `InitInstance` und `ExitInstance` Member-Funktionen zum Ausführen der Initialisierung und Beendigung, die die DLL erforderlich sind. Weitere Informationen finden Sie unter den [regular MFC-DLLs initialisieren](#initializing-regular-dlls) Abschnitt.

> [!WARNING]
> Es gibt erhebliche Einschränkungen auf sichere Weise in eine DLL-Einstiegspunkt Möglichkeiten. Finden Sie unter [allgemein empfohlene Vorgehensweisen](/windows/desktop/Dlls/dynamic-link-library-best-practices) für bestimmte Windows-APIs, die in Aufrufen unsicher sind `DllMain`. Wenn Sie einen anderen Wert müssen die einfachste Initialisierung klicken Sie dann verwenden Sie keine Initialisierungsfunktion für die DLL. Sie können festlegen, müssen die Initialisierungsfunktion, nach dem Aufrufen von, `DllMain` hat ausgeführt wurde und bevor sie anderen Funktionen in die DLL aufrufen.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Normale (MFC-Fremd)-DLLs initialisieren

Für die eigene Initialisierung in normalen (MFC-Fremd) DLLs, mit denen die VCRuntime bereitgestellter `_DllMainCRTStartup` Einstiegspunkt, enthalten Ihre DLL-Quellcode muss eine Funktion namens `DllMain`. Der folgende Code zeigt einen grundlegenden Skelett, mit welcher der Definition der `DllMain` beispielsweise wie folgt aussehen:

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
> Ältere Windows-SDK-Dokumentation besagt, dass es sich bei der tatsächliche Namen der DLL-Einstiegspunkt-Funktion in der Linkerbefehlszeile mit der Option/Entry angegeben werden muss. Mit Visual C++, Sie müssen nicht die Option/Entry verwenden, wenn der Name Ihrer Funktion Einstiegspunkt `DllMain`. In der Tat bei Verwendung der Option/Entry und Name Ihr Einstiegspunkt funktioniert etwas anders als `DllMain`, die CRT ist nicht ordnungsgemäß initialisiert abrufen, es sei denn, Ihre Einstiegspunktfunktion der gleichen Initialisierung, die aufruft `_DllMainCRTStartup` macht.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Reguläre MFC-DLLs initialisieren

Da die reguläre MFC-DLLs haben eine `CWinApp` Objekt ist, sollten sie ihre Aufgaben Initialisierungs- und Terminierungscode in am gleichen Speicherort wie einer MFC-Anwendung ausführen: in der `InitInstance` und `ExitInstance` Memberfunktionen von der DLLs `CWinApp`-abgeleitet -Klasse. Da MFC bietet eine `DllMain` -Funktion, die aufgerufen wird, werden `_DllMainCRTStartup` für `DLL_PROCESS_ATTACH` und `DLL_PROCESS_DETACH`, sollten Sie keinen eigenen `DllMain` Funktion. Der vom MFC bereitgestellten `DllMain` Funktionsaufrufe `InitInstance` beim Laden der DLL, und er ruft `ExitInstance` , bevor die DLL entladen wird.

Einer regulären MFC DLL kann von mehreren Threads durch verfolgt Aufrufen [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc) und [TlsGetValue](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) in seine `InitInstance` Funktion. Diese Funktionen ermöglichen die DLL für threadspezifische Daten nachzuverfolgen.

In der regulären MFC-DLL, die dynamisch mit MFC, verknüpft Wenn Sie alle MFC-OLE, MFC-Datenbank (oder DAO) verwenden oder MFC-Sockets, bzw. unterstützt die Debug-MFC-Erweiterungs-DLLs MFCO*Version*D.dll, MFCD*Version*D.dll und MFCN*Version*D.dll (wobei *Version* ist die Versionsnummer) automatisch verknüpft sind. Müssen Sie eine der folgenden vordefinierten Initialisierungsfunktionen aufrufen, für jede dieser DLLs, die Sie in Ihrem regulären MFC DLL des verwenden `CWinApp::InitInstance`.

|Typ der MFC-Unterstützung|Die Initialisierungsfunktion aufrufen|
|-------------------------|-------------------------------------|
|MFC-OLE (MFCO*Version*D.dll)|`AfxOleInitModule`|
|MFC-Datenbank (MFCD*Version*D.dll)|`AfxDbInitModule`|
|MFC-Sockets (MFCN*Version*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC-Erweiterungs-DLLs initialisieren

Da MFC-Erweiterungs-DLLs keine `CWinApp`-abgeleitete Objekt (wie reguläre MFC-DLLs), sollten Sie Ihre Initialisierungs- und Terminierungscode Code zum Hinzufügen der `DllMain` Funktion, die die MFC-DLL-Assistenten generiert.

Der Assistent bietet den folgenden Code für die MFC-Erweiterungs-DLLs. Im Code `PROJNAME` ist ein Platzhalter für den Namen des Projekts.

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

Erstellen eines neuen `CDynLinkLibrary` Objekt während der Initialisierung ermöglicht die MFC-Erweiterungs-DLL exportieren `CRuntimeClass` Objekte oder Ressourcen, um die Client-Anwendung.

Wenn Sie beabsichtigen, die MFC-Erweiterungs-DLL von ein oder mehrere reguläre MFC-DLLs verwenden, müssen Sie keine Initialisierungsfunktion, die erstellt Exportieren einer `CDynLinkLibrary` Objekt. Von jedem der regulären MFC-DLLs, die die MFC-Erweiterungs-DLL zu verwenden, muss diese Funktion aufgerufen werden. Befindet sich in eine geeignete Stelle zum Aufrufen dieser Initialisierungsfunktion der `InitInstance` Memberfunktion die regulären MFC DLL `CWinApp`-abgeleitetes Objekt vor der Verwendung von der MFC-Erweiterungs-DLLs exportierten Klassen oder Funktionen.

In der `DllMain` , dass die MFC-DLL-Assistenten generiert, den Aufruf von `AfxInitExtensionModule` erfasst die Modul Laufzeit-Klassen (`CRuntimeClass` Strukturen) sowie die Objektfactory (`COleObjectFactory` Objekte) für die Verwendung der `CDynLinkLibrary` Objekt erstellt wird. Sie sollten überprüfen, dass den Rückgabewert von `AfxInitExtensionModule`; Wenn ein NULL-Wert, von zurückgegeben wird `AfxInitExtensionModule`, Zurückgeben von 0 (null), von Ihrer `DllMain` Funktion.

Wenn der MFC-Erweiterungs-DLL in eine ausführbare Datei explizit verknüpft wird (d. h. die ausführbare Datei ruft `AfxLoadLibrary` zur DLL verknüpfen), sollten Sie einen Aufruf hinzufügen `AfxTermExtensionModule` auf `DLL_PROCESS_DETACH`. Mit dieser Funktion können MFC zum Bereinigen von den MFC-Erweiterungs-DLL, wird jeder Prozess von der MFC-Erweiterungs-DLL getrennt (Dies ist der Fall, wenn der Prozess beendet wird oder die DLL, aufgrund entladen wird einer `AfxFreeLibrary` aufrufen). Wenn der MFC-Erweiterungs-DLL implizit an die Anwendung, die den Aufruf von verknüpft wird `AfxTermExtensionModule` ist nicht erforderlich.

Anwendungen, die explizit die Verknüpfung mit MFC-Erweiterungs-DLLs aufrufen muss `AfxTermExtensionModule` beim Freigeben von der DLL. Sie sollten auch verwenden, `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle der Win32-Funktionen `LoadLibrary` und `FreeLibrary`) Wenn die Anwendung mehrere Threads verwendet. Mithilfe von `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass den starten und Herunterfahren Code, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL geladen und entladen den globalen MFC-Status nicht beschädigt ist.

Da MFCx0.dll vollständig, mit der Zeit initialisiert wurde `DllMain` ist aufgerufen wird, können Sie Speicher zuordnen und Aufrufen von MFC-Funktionen in `DllMain` (im Gegensatz zu den 16-Bit-Version von MFC).

Erweiterungs-DLLs kümmern multithreading durch Behandeln der `DLL_THREAD_ATTACH` und `DLL_THREAD_DETACH` Fälle, der `DllMain` Funktion. Diese Fälle werden übergeben, um `DllMain` Wenn Threads Anfügen und Trennen von aus der DLL. Aufrufen von [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc) beim Anfügen an eine DLL ist, kann die DLL zu Threads Verwalten lokaler Speicher (TLS) indiziert werden, für jeden Thread angefügt wird, auf die DLL.

Beachten Sie, dass die Headerdatei "afxdllx.h" spezielle Definitionen für Strukturen, die in MFC-Erweiterungs-DLLs, z. B. die Definition für die verwendete enthält `AFX_EXTENSION_MODULE` und `CDynLinkLibrary`. Sie sollten diese Headerdatei in der MFC-Erweiterungs-DLL verwenden.

> [!NOTE]
>  Es ist wichtig, dass Sie weder definieren noch keines der `_AFX_NO_XXX` Makros in "stdafx.h". Diese Makros sind nur zum Überprüfen, ob eine bestimmte Zielplattform dieses Feature oder nicht unterstützt vorhanden. Sie können das Programm überprüft diese Makros schreiben (z. B. `#ifndef _AFX_NO_OLE_SUPPORT`), aber Ihr Programm sollte nie definieren, oder heben Sie die Definition dieser Makros.

Eine Beispiel-Initialisierung-Funktion, die multithreading behandelt befindet sich im [Using Thread Local Storage in einer Dynamic Link Library](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library) im Windows SDK. Beachten Sie, dass das Beispiel eine Einstiegspunktfunktion Namens enthält `LibMain`, aber Sie sollten diese Funktion benennen `DllMain` , damit sie mit der MFC und C-Laufzeitbibliotheken funktioniert.

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)<br/>
[DllMain-Einstiegspunkt](/windows/desktop/Dlls/dllmain)<br/>
[Dynamic Link Library, bewährte Methoden](/windows/desktop/Dlls/dynamic-link-library-best-practices)