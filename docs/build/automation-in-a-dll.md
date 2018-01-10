---
title: Automatisierung in einer DLL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e3630aab764988ad86e6120301dfff548ad4368
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="automation-in-a-dll"></a>Automatisierung in einer DLL
Wenn Sie die Automatisierungsoption im MFC-DLL-Assistenten auswählen, bietet der Assistent Sie wie folgt:  
  
-   Ein Starter-Objekt-Datenbeschreibungssprache (. ODL)-Datei  
  
-   Eine Include-Direktive in der Datei "stdafx.h" Afxole.h  
  
-   Eine Implementierung von der `DllGetClassObject` -Funktion, die Aufrufe der **AfxDllGetClassObject** Funktion  
  
-   Eine Implementierung von der `DllCanUnloadNow` -Funktion, die Aufrufe der **AfxDllCanUnloadNow** Funktion  
  
-   Eine Implementierung von der `DllRegisterServer` -Funktion, die Aufrufe der [COleObjectFactory:: UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) Funktion  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Automatisierungsserver](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)