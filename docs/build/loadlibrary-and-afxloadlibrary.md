---
title: "\"LoadLibrary\" und \"AfxLoadLibrary\""
description: Verwenden von LoadLibrary und AfxLoadLibrary für Explizites Laden von DLLs in MSVC.
ms.date: 01/28/2020
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: f803212c4485f7517dc42802f1ff581ffa4e609d
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821537"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>"LoadLibrary" und "AfxLoadLibrary"

Prozesse aufrufen [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) oder [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) , um explizit eine Verknüpfung mit einer DLL zu herstellen. (MFC-Apps verwenden [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary) oder [afxloadlibraryex](../mfc/reference/application-information-and-management.md#afxloadlibraryex).) Wenn die Funktion erfolgreich ausgeführt wird, ordnet Sie die angegebene DLL dem Adressraum des aufrufenden Prozesses zu und gibt ein Handle für die DLL zurück. Das Handle ist in anderen Funktionen erforderlich, die für die explizite Verknüpfung verwendet werden – z. b. `GetProcAddress` und `FreeLibrary`. Weitere Informationen finden Sie unter [explizites verknüpfen](linking-an-executable-to-a-dll.md#linking-explicitly).

`LoadLibrary` versucht, die DLL mithilfe derselben Suchfolge aufzufinden, die für die implizite Verknüpfung verwendet wird. `LoadLibraryEx` bietet Ihnen mehr Kontrolle über die Reihenfolge der Suchpfade. Weitere Informationen finden Sie unter [Dynamic Link Library Search Order](/windows/win32/dlls/dynamic-link-library-search-order). Wenn das System die dll nicht finden kann oder wenn die Einstiegspunkt Funktion false zurückgibt, gibt `LoadLibrary` NULL zurück. Wenn im Aufruf von `LoadLibrary` ein DLL-Modul angegeben ist, das bereits im Adressraum des aufrufenden Prozesses zugeordnet ist, gibt die Funktion einfach ein Handle für die DLL zurück und erhöht den Referenzzähler des Moduls.

Wenn die dll über eine Einstiegspunkt Funktion verfügt, ruft das Betriebssystem die Funktion im Kontext des Threads auf, der `LoadLibrary` oder `LoadLibraryEx`aufgerufen hat. Die Einstiegspunkt Funktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt ist. Dies ist der Fall, wenn ein vorheriger-`LoadLibrary` oder `LoadLibraryEx` für die dll keinen entsprechenden Aufrufder `FreeLibrary`-Funktion enthielt.

Für MFC-Anwendungen, die MFC-Erweiterungs-DLLs laden, empfiehlt es sich, `AfxLoadLibrary` oder `AfxLoadLibraryEx` anstelle von `LoadLibrary` oder `LoadLibraryEx`zu verwenden. Die MFC-Funktionen behandeln die Thread Synchronisierung vor dem expliziten Laden der dll. Die Schnittstellen (Funktionsprototypen) zum `AfxLoadLibrary` und `AfxLoadLibraryEx` sind identisch mit `LoadLibrary` und `LoadLibraryEx`.

Wenn Windows die dll nicht laden kann, kann der Prozess versuchen, nach dem Fehler eine Wiederherstellung durchführen. Beispielsweise kann der Benutzer den Fehler benachrichtigen und dann einen weiteren Pfad zur DLL anfordern.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie den vollständigen Pfad aller DLLs angeben. Das aktuelle Verzeichnis wird möglicherweise zuerst durchsucht, wenn Dateien von `LoadLibrary`geladen werden. Wenn Sie den Pfad der Datei nicht vollständig qualifizieren, wird möglicherweise eine andere Datei als die beabsichtigte geladen. Wenn Sie eine DLL erstellen, verwenden Sie die [/DEPENDENTLOADFLAG](reference/dependentloadflag.md) -Linkeroption, um eine Such Reihenfolge für statisch verknüpfte DLL-Abhängigkeiten anzugeben. Verwenden Sie in ihren DLLs sowohl die Complete-Pfade zum expliziten Laden von Abhängigkeiten als auch das `LoadLibraryEx` oder `AfxLoadLibraryEx`, um die Such Reihenfolge der Module anzugeben. Weitere Informationen finden Sie unter [Dynamic-Link Library Security](/windows/win32/dlls/dynamic-link-library-security) und [Dynamic Link Library Search Order](/windows/win32/dlls/dynamic-link-library-search-order).

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Such Reihenfolge der Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary und AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Siehe auch

- [Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
