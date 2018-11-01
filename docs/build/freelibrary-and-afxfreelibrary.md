---
title: "\"FreeLibrary\" und \"AfxFreeLibrary\""
ms.date: 11/04/2016
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
ms.openlocfilehash: ce52eb43fa8f371b68d836f01163003f056f34c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530233"
---
# <a name="freelibrary-and-afxfreelibrary"></a>"FreeLibrary" und "AfxFreeLibrary"

Prozesse, die explizite mit einer DLL-Aufrufs Verknüpfung der [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) funktionieren, wenn die DLL-Modul nicht mehr benötigt wird. Dieser Funktion verringert die Anzahl der Verweise des Moduls und, wenn der Verweiszähler NULL ist, wird herab aus dem Adressraum des Prozesses.

In einer MFC-Anwendung verwenden ["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary) anstelle von `FreeLibrary` , eine MFC-Erweiterungs-DLL zu entladen. Die Schnittstelle (Funktionsprototyp) für `AfxFreeLibrary` ist identisch mit `FreeLibrary`.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bestimmen Sie welche Verknüpfungsmethode verwendet werden](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary)