---
title: "Konflikt mit dem x86-Compiler"
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
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
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