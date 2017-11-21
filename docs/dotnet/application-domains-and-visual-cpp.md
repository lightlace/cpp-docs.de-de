---
title: "Anwendungsdomänen und Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 57a45bd6f73040623fe90626b1c3896df3258dd8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="application-domains-and-visual-c"></a>Anwendungsdomänen und Visual C++
Wenn Sie haben eine `__clrcall` virtuelle Funktion, werden die Vtable pro Anwendungsdomäne (Appdomain). Wenn Sie ein Objekt in einer Appdomain erstellen, können Sie nur die virtuelle Funktion von innerhalb dieser Appdomain aufrufen. Alle Funktionen in **/CLR: pure** Compilands verwenden die `__clrcall` Aufrufkonvention. Aus diesem Grund alle v-Tabellen definiert, **/CLR: pure** Compilands sind pro-Appdomain. Im gemischten Modus (**"/ CLR"**) müssen pro Prozess-v-Tabellen, wenn der Typ keine enthält `__clrcall` virtuelle Funktionen. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 Weitere Informationen finden Sie unter  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [Vorgehensweise: Migrieren auf/CLR: pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)