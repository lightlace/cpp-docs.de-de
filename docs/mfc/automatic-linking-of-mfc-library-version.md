---
title: Automatisches Verlinken der MFC-Bibliotheksversion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: defaultlib
dev_langs: C++
helpviewer_keywords:
- defaultlib in MFC
- automatic links [MFC]
- MFC libraries, linking to
- linking [MFC], automatic of MFC library version
- linking [MFC]
- linking [MFC], of MFC
- MFC libraries, versions
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ddc156d8518318a686796a25e89ee84a9a67ee59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="automatic-linking-of-mfc-library-version"></a>Automatisches Verlinken der MFC-Bibliotheksversion
In MFC-Versionen vor Version 3.0 (vor Visual C++, Version 2.0) mussten Sie manuell die richtige Version der MFC-Bibliothek in der Eingabeliste von Bibliotheken für den Linker angeben. Mit MFC, Version 3.0 und höher ist es nicht mehr notwendig, dass die Version der MFC-Bibliothek manuell angeben. Die MFC-Headerdateien bestimmt stattdessen automatisch die richtige Version der MFC-Bibliothek, basierend auf Werten, die mit definierten `#define`, wie z. B. **_DEBUG** oder **_UNICODE**. Hinzufügen von MFC-Headerdateien **Option** Direktiven, die den Linker angewiesen, die in einer bestimmten Version der MFC-Bibliothek zu verknüpfen.  
  
 Z. B. das folgende Codefragment aus der AFX. H-Headerdatei weist den Linker an, entweder der NAFXCWD verknüpfen. LIB- oder der NAFXCW. LIB-Version von MFC, je nachdem, ob Sie die Debugversion von MFC verwenden:  
  
```c++
#ifndef _UNICODE 
#ifdef _DEBUG
#pragma comment(lib, "nafxcwd.lib")
#else
#pragma comment(lib, "nafxcw.lib")
#endif
#else
#ifdef _DEBUG
#pragma comment(lib, "uafxcwd.lib")
#else
#pragma comment(lib, "uafxcw.lib")
#endif
#endif
```  
  
 MFC-Headerdateien link auch alle erforderlichen Bibliotheken, einschließlich der MFC-Bibliotheken, Win32-Bibliotheken, OLE-Bibliotheken, OLE-Bibliotheken, die aus Beispielen erstellt, ODBC-Bibliotheken und So weiter. Die Win32-Bibliotheken enthalten Kernel32.Lib, User32.Lib und gdi32.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Bibliotheksversionen](../mfc/mfc-library-versions.md)

