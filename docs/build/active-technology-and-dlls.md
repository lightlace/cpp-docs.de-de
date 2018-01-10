---
title: Active Technology und DLLs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44dcc58aed4025af2e3e2177e978633c13f0ef20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="active-technology-and-dlls"></a>Active Technology und DLLs
Active Technology ermöglicht Objektserver vollständig innerhalb einer DLL implementiert werden. Diese Art des Servers ist einen in-Process-Server bezeichnet. MFC unterstützt vollständig in-Process-Server für alle Funktionen der visuellen Bearbeitung nicht hauptsächlich da Active-Technologie eine Möglichkeit für einen Server zu verbinden, in die Hauptnachrichtenschleife des Containers nicht bietet. MFC erfordert Zugriff auf die containeranwendung Nachrichtenschleife, Zugriffstasten und leerlaufzeitverarbeitung zu behandeln.  
  
 Wenn Sie eines Automatisierungsservers schreiben, und der Server keine Benutzeroberfläche hat, können Sie Ihre Server in-Process-Server festlegen und speichern diese vollständig in eine DLL.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Automatisierungsserver](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)