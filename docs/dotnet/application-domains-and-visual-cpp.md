---
title: Anwendungsdomänen und Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ddb60b3fad6c230677e2098dd89a723198bea8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="application-domains-and-visual-c"></a>Anwendungsdomänen und Visual C++
Wenn Sie haben eine `__clrcall` virtuelle Funktion, werden die Vtable pro Anwendungsdomäne (Appdomain). Wenn Sie ein Objekt in einer Appdomain erstellen, können Sie nur die virtuelle Funktion von innerhalb dieser Appdomain aufrufen. Im gemischten Modus (**"/ CLR"**) müssen pro Prozess-v-Tabellen, wenn der Typ keine enthält `__clrcall` virtuelle Funktionen. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Weitere Informationen finden Sie unter  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)