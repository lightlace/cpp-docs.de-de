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
ms.openlocfilehash: c7700dd865e320686a2ad8bd036f207b9ecee6ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493206"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>"LoadLibrary" und "AfxLoadLibrary"

Prozesse aufrufen [loadlibraryexa](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) oder [LoadLibraryExW](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) (oder [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)), um explizit eine Verknüpfung mit einer DLL zu erhalten. Wenn der Aufruf erfolgreich ist, ordnet die Funktion die angegebene DLL im Adressbereich des aufrufenden Prozesses zu und gibt ein Handle für die DLL zurück. Dieses Handle kann zusammen mit anderen Funktionen, beispielsweise `GetProcAddress` und `FreeLibrary`, für die explizite Verknüpfung verwendet werden.

`LoadLibrary` versucht, die DLL mithilfe derselben Suchfolge aufzufinden, die für die implizite Verknüpfung verwendet wird. Wenn das System die DLL nicht finden kann oder die Einstiegspunktfunktion FALSE zurückgibt, wird von `LoadLibrary` zurückgegeben. Wenn im Aufruf von `LoadLibrary` ein DLL-Modul angegeben ist, das bereits im Adressraum des aufrufenden Prozesses zugeordnet ist, gibt die Funktion einfach ein Handle für die DLL zurück und erhöht den Referenzzähler des Moduls.

Wenn die DLL über eine Einstiegspunktfunktion verfügt, ruft das Betriebssystem die Funktion im Kontext des Threads auf, durch den `LoadLibrary` aufgerufen wurde. Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt ist, da es einen früheren Aufruf von `LoadLibrary` ohne entsprechenden Aufruf der `FreeLibrary`-Funktion gegeben hat.

Für MFC-Anwendungen, die MFC-Erweiterungs-DLLs laden, empfiehlt `AfxLoadLibrary` es sich `LoadLibrary`, anstelle von zu verwenden. `AfxLoadLibrary` behandelt die Threadsynchronisierung vor dem Aufruf von `LoadLibrary`. Die Schnittstelle (Funktionsprototyp) zu `AfxLoadLibrary` ist mit `LoadLibrary` identisch.

Wenn die DLL von Windows nicht geladen werden kann, versucht der Prozess, die Verarbeitung fortzusetzen. So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie den vollständigen Pfad aller DLLs angeben. Das aktuelle Verzeichnis wird zuerst durchsucht, wenn Dateien geladen werden. Wenn Sie den Pfad für die Datei nicht qualifizieren, wird unter Umständen eine falsche Datei geladen. Eine andere Möglichkeit, dies zu verhindern, ist die Verwendung der Option [/DEPENDENTLOADFLAG](reference/dependentloadflag.md) Linker.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Such Reihenfolge der Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary und AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Siehe auch

- [Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
