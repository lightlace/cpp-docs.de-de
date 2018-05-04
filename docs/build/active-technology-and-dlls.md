---
title: Active Technology und DLLs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5e0296b994f7944d5b26e98ba1b0545a03ec55b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="active-technology-and-dlls"></a>Active Technology und DLLs
Active Technology ermöglicht Objektserver vollständig innerhalb einer DLL implementiert werden. Diese Art des Servers ist einen in-Process-Server bezeichnet. MFC unterstützt vollständig in-Process-Server für alle Funktionen der visuellen Bearbeitung nicht hauptsächlich da Active-Technologie eine Möglichkeit für einen Server zu verbinden, in die Hauptnachrichtenschleife des Containers nicht bietet. MFC erfordert Zugriff auf die containeranwendung Nachrichtenschleife, Zugriffstasten und leerlaufzeitverarbeitung zu behandeln.  
  
 Wenn Sie eines Automatisierungsservers schreiben, und der Server keine Benutzeroberfläche hat, können Sie Ihre Server in-Process-Server festlegen und speichern diese vollständig in eine DLL.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Automatisierungsserver](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)