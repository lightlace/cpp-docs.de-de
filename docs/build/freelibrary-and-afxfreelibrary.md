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
ms.openlocfilehash: 709e4fdbc24d6fbbac44944e686a6fecf8c9b8db
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808143"
---
# <a name="freelibrary-and-afxfreelibrary"></a>"FreeLibrary" und "AfxFreeLibrary"

Prozesse, die explizite mit einer DLL-Aufrufs Verknüpfung der [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) funktionieren, wenn die DLL-Modul nicht mehr benötigt wird. Dieser Funktion verringert die Anzahl der Verweise des Moduls und, wenn der Verweiszähler NULL ist, wird herab aus dem Adressraum des Prozesses.

In einer MFC-Anwendung verwenden ["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary) anstelle von `FreeLibrary` , eine MFC-Erweiterungs-DLL zu entladen. Die Schnittstelle (Funktionsprototyp) für `AfxFreeLibrary` ist identisch mit `FreeLibrary`.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [LoadLibrary und AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
