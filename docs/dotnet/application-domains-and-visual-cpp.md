---
title: "Anwendungsdomänen und Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6c1af6f5054d6d04f2933e9fedc2a4e8373efe8b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="application-domains-and-visual-c"></a>Anwendungsdomänen und Visual C++
Wenn Sie haben eine `__clrcall` virtuelle Funktion, werden die Vtable pro Anwendungsdomäne (Appdomain). Wenn Sie ein Objekt in einer Appdomain erstellen, können Sie nur die virtuelle Funktion von innerhalb dieser Appdomain aufrufen. Im gemischten Modus (**"/ CLR"**) müssen pro Prozess-v-Tabellen, wenn der Typ keine enthält `__clrcall` virtuelle Funktionen. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Weitere Informationen finden Sie unter  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)