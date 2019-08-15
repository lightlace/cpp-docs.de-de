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
ms.openlocfilehash: 9c657bb0d583270f81658afa53f36b1be6a4fd4a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493267"
---
# <a name="freelibrary-and-afxfreelibrary"></a>"FreeLibrary" und "AfxFreeLibrary"

Prozesse, die explizit mit einer DLL verknüpfen, rufen die [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) -Funktion auf, wenn das dll-Modul nicht mehr benötigt wird. Diese Funktion Dekremente den Verweis Zähler des Moduls. wenn der Verweis Zähler Null ist, wird er vom Adressraum des Prozesses entfernt.

Verwenden Sie in einer MFC-Anwendung [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) anstelle `FreeLibrary` von, um eine MFC-Erweiterungs-DLL zu entladen. Die-Schnittstelle (Funktionsprototyp `AfxFreeLibrary` ) für ist `FreeLibrary`identisch mit.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [LoadLibrary und AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
