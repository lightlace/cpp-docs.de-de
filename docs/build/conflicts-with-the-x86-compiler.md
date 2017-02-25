---
title: "Konflikt mit dem x86-Compiler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Konflikt mit dem x86-Compiler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Datentypen, die größer als 4 Bytes sind, werden nicht automatisch auf dem Stapel ausgerichtet, wenn Sie mithilfe des x86\-Compilers eine Anwendung kompilieren.  Da die Architektur für den x86\-Compiler ein 4 Bytes ausgerichteter Stapel ist, kann alles, was größer als 4 Bytes ist, z. B. eine 64\-Bit\-Ganzzahl, nicht automatisch an einer 8\-Byte\-Adresse ausgerichtet werden.  
  
 Mit nicht ausgerichteten Daten zu arbeiten hat zwei Auswirkungen.  
  
-   Es dauert möglicherweise länger, auf nicht ausgerichtete Speicherorte zuzugreifen, als auf ausgerichtete.  
  
-   Nicht ausgerichtete Speicherorte können nicht in zusammengefügten Vorgängen verwendet werden.  
  
 Wenn Sie eine strengere Ausrichtung benötigen, verwenden Sie `__declspec(align(N)) on your variable declarations`.  Dies bewirkt, dass der Compiler den Stapel dynamisch ausrichtet, um der Spezifikation zu entsprechen.  Den Stapel dynamisch zur Laufzeit einzustellen verursacht möglicherweise jedoch eine langsamere Ausführung der Anwendung.  
  
## Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)   
 [align](../cpp/align-cpp.md)