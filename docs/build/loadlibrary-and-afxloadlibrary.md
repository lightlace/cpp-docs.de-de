---
title: "\"LoadLibrary\" und \"AfxLoadLibrary\""
ms.date: 05/24/2018
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: 96b8c0ce1116dbb08260573f25f941ca54169127
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822417"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>"LoadLibrary" und "AfxLoadLibrary"

Verarbeitet Aufruf [LoadLibraryExA](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) oder [LoadLibraryExW](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexw)(oder [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) explizit mit einer DLL verknüpfen. Wenn der Aufruf erfolgreich ist, ordnet die Funktion die angegebene DLL im Adressbereich des aufrufenden Prozesses zu und gibt ein Handle für die DLL zurück. Dieses Handle kann zusammen mit anderen Funktionen, beispielsweise `GetProcAddress` und `FreeLibrary`, für die explizite Verknüpfung verwendet werden.

`LoadLibrary` versucht, die DLL mithilfe derselben Suchfolge aufzufinden, die für die implizite Verknüpfung verwendet wird. Wenn das System die DLL nicht finden kann oder die Einstiegspunktfunktion FALSE zurückgibt, wird von `LoadLibrary` zurückgegeben. Wenn im Aufruf von `LoadLibrary` ein DLL-Modul angegeben ist, das bereits im Adressraum des aufrufenden Prozesses zugeordnet ist, gibt die Funktion einfach ein Handle für die DLL zurück und erhöht den Referenzzähler des Moduls.

Wenn die DLL über eine Einstiegspunktfunktion verfügt, ruft das Betriebssystem die Funktion im Kontext des Threads auf, durch den `LoadLibrary` aufgerufen wurde. Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt ist, da es einen früheren Aufruf von `LoadLibrary` ohne entsprechenden Aufruf der `FreeLibrary`-Funktion gegeben hat.

Für MFC-Anwendungen, die MFC-Erweiterungs-DLLs laden, empfehlen wir die Verwendung von `AfxLoadLibrary` anstelle von `LoadLibrary`. `AfxLoadLibrary` behandelt die Threadsynchronisierung vor dem Aufruf von `LoadLibrary`. Die Schnittstelle (Funktionsprototyp) zu `AfxLoadLibrary` ist mit `LoadLibrary` identisch.

Wenn die DLL von Windows nicht geladen werden kann, versucht der Prozess, die Verarbeitung fortzusetzen. So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.

> [!IMPORTANT]
> Stellen Sie sicher, dass alle DLLs, die den vollständigen Pfad angeben. Das aktuelle Verzeichnis wird zuerst durchsucht, wenn die Dateien geladen werden. Wenn Sie den Pfad für die Datei nicht qualifizieren, wird unter Umständen eine falsche Datei geladen. Eine weitere Möglichkeit, dies zu verhindern, ist die Verwendung der [/DEPENDENTLOADFLAG](reference/dependentloadflag.md) -Linkeroption.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Dynamic Link Library Search Order](/windows/desktop/Dlls/dynamic-link-library-search-order)

- [FreeLibrary und AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Siehe auch

- [DLLs in Visual C++](dlls-in-visual-cpp.md)
