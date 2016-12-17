---
title: "Erstellen isolierter C/C++-Anwendungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Isolierte Anwendungen [C++]"
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen isolierter C/C++-Anwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine isolierte Anwendung ist nur von parallelen Assemblys abhängig und stellt die Bindung zu den abhängigen Assemblys mithilfe eines Manifests her.  Die Anwendung muss nicht vollständig isoliert sein, um unter Windows ordnungsgemäß ausgeführt zu werden. Wenn Sie die Anwendung vollständig isolieren, sparen Sie jedoch möglicherweise Zeit bei der späteren Wartung der Anwendung.  Weitere Informationen zu den Vorteilen der vollständigen Isolation von Anwendungen finden Sie unter [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190).  
  
 Beim Erstellen einer systemeigenen C\/C\+\+\-Anwendung mit Visual C\+\+ generiert das Visual Studio\-Projektsystem standardmäßig eine Manifestdatei, die die Abhängigkeiten der Anwendung von Visual C\+\+\-Bibliotheken beschreibt.  Wenn die Anwendung lediglich über diese Abhängigkeiten verfügt, wird sie zu einer isolierten Anwendung, sobald sie mit Visual Studio erneut erstellt wird.  Wenn die Anwendung zur Laufzeit andere Bibliotheken verwendet, müssen Sie diese Bibliotheken möglicherweise als parallele Assemblys erneut erstellen. Folgen Sie dazu den in [Erstellen von parallelen C\/C\+\+\-Assemblys](../build/building-c-cpp-side-by-side-assemblies.md) beschriebenen Schritten.  
  
## Siehe auch  
 [Konzept der isolierten Anwendungen und der parallelen Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys \(C\/C\+\+\)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)