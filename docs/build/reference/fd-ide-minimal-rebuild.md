---
title: "/FD (Minimale Neuerstellung in der IDE) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/FD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FD (Compileroption) [C++]"
  - "FD (Compileroption) [C++]"
  - "-FD (Compileroption) [C++]"
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /FD (Minimale Neuerstellung in der IDE)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/FD** wird Benutzern nur im Dialogfeld **Eigenschaftenseiten** des C\+\+\-Projekts in der Eigenschaftenseite der [Befehlszeile](../../ide/command-line-property-pages.md) angezeigt, und zwar genau dann, wenn nicht auch [\/Gm \(Minimale Neuerstellung aktivieren\)](../../build/reference/gm-enable-minimal-rebuild.md) ausgewählt ist.  **\/FD** ist lediglich in der Entwicklungsumgebung wirksam.  **\/FD** wird in der Ausgabe von **cl \/?** nicht angezeigt.  
  
 Wenn Sie in der Entwicklungsumgebung **\/Gm** nicht aktivieren, wird **\/FD** verwendet.  Über **\/FD** wird sichergestellt, dass die .idb\-Datei über ausreichende Abhängigkeitsinformationen verfügt.  **\/FD** wird ausschließlich von der Entwicklungsumgebung verwendet und sollte nicht in der Befehlszeile oder einem Buildskript verwendet werden.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)