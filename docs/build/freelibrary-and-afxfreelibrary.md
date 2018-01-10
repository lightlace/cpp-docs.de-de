---
title: "\"FreeLibrary\" und \"AfxFreeLibrary\" | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs: C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d5f2c1cce980f97e7a99ff2347daceac05f984f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="freelibrary-and-afxfreelibrary"></a>"FreeLibrary" und "AfxFreeLibrary"
Prozesse, die die explizite mit einer DLL-Aufruf Verknüpfung die [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) ausgeführt werden, wenn die DLL-Modul nicht mehr benötigt wird. Diese Funktion verringert Verweiszähler für das Modul, und, wenn der Verweiszähler NULL ist, herab aus dem Adressraum des Prozesses.  
  
 Verwenden Sie in einer MFC-Anwendung ["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary) anstelle von `FreeLibrary` eine MFC-Erweiterungs-DLL entladen. Die Schnittstelle (Funktionsprototyp) für `AfxFreeLibrary` ist identisch mit `FreeLibrary`.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Gewusst wie: implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Welche Verknüpfungsmethode ermitteln](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 ["AfxFreeLibrary"](../mfc/reference/application-information-and-management.md#afxfreelibrary)