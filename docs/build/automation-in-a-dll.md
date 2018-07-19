---
title: Automatisierung in einer DLL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41c5f31a72cf734296ecb281e0785d415c8043a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360653"
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