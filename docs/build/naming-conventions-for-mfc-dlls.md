---
title: "Namenskonventionen für MFC-DLLs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC libraries [C++], naming conventions
- naming conventions [C++], MFC DLLs
- MFC DLLs [C++], naming conventions
- libraries [C++], MFC DLL names
- shared DLL versions [C++]
- DLLs [C++], naming conventions
- DLLs [C++], library names
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f7702e9babcc4769136d6deab63b627f8b09bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="naming-conventions-for-mfc-dlls"></a>Namenskonventionen für MFC-DLLs
Verwenden Sie eine strukturierte Benennungskonvention, DLLs und Bibliotheken, die in MFC enthaltenen. Dies erleichtert es, wissen, welche DLL-Datei oder Bibliothek Sie für welchen Zweck verwendet werden soll.  
  
 Die Importbibliotheken zum Erstellen von Anwendungen oder MFC-Erweiterungs-DLLs, die diese DLLs verwenden den gleichen Basisnamen wie die DLL haben aber eine LIB-Dateinamenerweiterung.  
  
### <a name="shared-dll-naming-convention"></a>Gemeinsam genutzte DLL-Namenskonvention  
  
|DLL|Beschreibung|  
|---------|-----------------|  
|MFCx0.DLL|MFC-DLL, ANSI-Release-version|  
|MFCx0U.DLL|MFC-DLL, Unicode-Release-version|  
|MFCx0D.DLL|MFC-DLL, ANSI-Debugbuild|  
|MFCx0UD.DLL|MFC-DLL, Unicode-Debugversion|  
  
 Wenn Sie dynamisch der gemeinsam genutzten DLL-Version von MFC verknüpfen möchten, ob sie eine Anwendung oder eine MFC-Erweiterungs-DLL ist, müssen Sie MFCx0.DLL zu Ihrem Produkt einschließen. Wenn Sie Unicode-Unterstützung in Ihrer Anwendung benötigen, stattdessen MFCx0U.dll.  
  
 Wenn Sie die DLL statisch mit MFC verknüpfen, müssen Sie diese mit einem statischen MFC-Bibliotheken verknüpfen. Diese Versionen werden gemäß der Konvention benannt [N &#124; U] AFXCW [D]. LIB. Weitere Informationen finden Sie in der Tabelle "Static Link Bibliotheks-Benennungskonventionen" in [Bibliotheks-Benennungskonventionen](../mfc/library-naming-conventions.md) (MFC).  
  
 Eine Liste der Visual C++-DLLs, die mit Ihren Anwendungen verteilt werden können, finden Sie in der Datei Redist.txt in Visual Studio-Installation.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Die Namenskonvention für Bibliotheken](../mfc/library-naming-conventions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)