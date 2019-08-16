---
title: Beschränkungen für das verzögerte Laden von DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
ms.openlocfilehash: be5e5eb360f80e0b2ea9682f38f6787044cd3c63
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493075"
---
# <a name="constraints-of-delay-loading-dlls"></a>Beschränkungen für das verzögerte Laden von DLLs

Es gibt Einschränkungen hinsichtlich des verzögerten Ladens von Importen.

- Datenimporte können nicht unterstützt werden. Eine Problemumgehung besteht darin, den Datenimport explizit über `LoadLibrary` (oder `GetModuleHandle`, wenn Sie wissen, dass die Hilfsfunktion für das verzögerte Laden die DLL geladen hat) und `GetProcAddress` selbst zu handhaben.

- Ein verzögertes Laden von Kernel32.dll wird nicht unterstützt. Diese DLL ist erforderlich, damit die Routinen der Hilfsfunktion für das verzögerte Laden das verzögerte Laden durchführen können.

- Die [Bindung](binding-imports.md) von weitergeleiteten Einstiegspunkten wird nicht unterstützt.

- Das verzögerte Laden einer DLL führt möglicherweise nicht zum selben Verwalten des Prozesses, wenn pro Prozess stattfindende Initialisierungen vorhanden sind, die am Einstiegspunkt der verzögert geladenen DLL stattfinden. Zu anderen Fällen gehört der statische TLS (Thread lokaler Speicher), der mit [__declspec (Thread)](../../cpp/thread.md)deklariert wurde. dieser wird nicht verarbeitet, wenn `LoadLibrary`die dll über geladen wird. Der dynamische TLS ist über `TlsAlloc`, `TlsFree`, `TlsGetValue` und `TlsSetValue` immer noch zur Verwendung in statischen oder verzögert geladenen DLLs verfügbar.

- Statische (globale) Funktionszeiger sollten für importierte Funktionen erneut initialisiert werden, nach die Funktion erstmals aufgerufen wurde. Der Grund ist, dass der Funktionszeiger bei der ersten Verwendung auf den Thunk zeigt.

- Derzeit gibt es keine Möglichkeit, das Laden nur bestimmter Verfahren aus einer DLL bei Verwendung des normalen Importmechanismus zu verzögern.

- Benutzerdefinierte Aufrufkonventionen (wie die Verwendung von Bedingungscodes in x86-Architekturen) werden nicht unterstützt. Außerdem werden die Gleitkommaregister auf keiner Plattform gespeichert. Wenn Ihre benutzerdefinierte Hilfsroutine oder Hookroutinen Gleitkommatypen verwenden, müssen sie den Gleitkommazustand auf Computern mit Registeraufrufkonventionen mit Gleitkommaparametern vollständig speichern und wiederherstellen. Seien Sie vorsichtig mit dem verzögerten Laden der CRT-DLL, wenn Sie CRT-Funktionen aufrufen, die Gleitkommaparameter in einem numerischen Datenprozessorstapel in der Hilfsfunktion annehmen.

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](linker-support-for-delay-loaded-dlls.md)<br/>
[LoadLibrary-Funktion](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)<br/>
[GetModuleHandle-Funktion](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)<br/>
[GetProcAddress-Funktion](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)<br/>
[TlsAlloc-Funktion](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)<br/>
[TlsFree-Funktion](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)<br/>
[TlsGetValue-Funktion](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)<br/>
[TlsSetValue-Funktion](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
