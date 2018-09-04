---
title: "\"FreeLibrary\" und \"AfxFreeLibrary\" | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs:
- C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 063c858253c12cfedbf252a124029b8cbc16a691
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680962"
---
# <a name="freelibrary-and-afxfreelibrary"></a>"FreeLibrary" und "AfxFreeLibrary"
Prozesse, die explizite mit einer DLL-Aufrufs Verknüpfung der [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152(v=vs.85).aspx) funktionieren, wenn die DLL-Modul nicht mehr benötigt wird. Dieser Funktion verringert die Anzahl der Verweise des Moduls und, wenn der Verweiszähler NULL ist, wird herab aus dem Adressraum des Prozesses.  
  
 In einer MFC-Anwendung verwenden ["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary) anstelle von `FreeLibrary` , eine MFC-Erweiterungs-DLL zu entladen. Die Schnittstelle (Funktionsprototyp) für `AfxFreeLibrary` ist identisch mit `FreeLibrary`.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Bestimmen Sie welche Verknüpfungsmethode verwendet werden](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152(v=vs.85).aspx)   
 ["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary)