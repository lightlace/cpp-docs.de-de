---
title: "/FD (Minimale Neuerstellung in der IDE)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /FD (Minimale Neuerstellung in der IDE)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/FD** wird Benutzern nur im Dialogfeld **Eigenschaftenseiten** des C\+\+\-Projekts in der Eigenschaftenseite der [Befehlszeile](../../ide/command-line-property-pages.md) angezeigt, und zwar genau dann, wenn nicht auch [\/Gm \(Minimale Neuerstellung aktivieren\)](../../build/reference/gm-enable-minimal-rebuild.md) ausgewählt ist.  **\/FD** ist lediglich in der Entwicklungsumgebung wirksam.  **\/FD** wird in der Ausgabe von **cl \/?** nicht angezeigt.  
  
 Wenn Sie in der Entwicklungsumgebung **\/Gm** nicht aktivieren, wird **\/FD** verwendet.  Über **\/FD** wird sichergestellt, dass die .idb\-Datei über ausreichende Abhängigkeitsinformationen verfügt.  **\/FD** wird ausschließlich von der Entwicklungsumgebung verwendet und sollte nicht in der Befehlszeile oder einem Buildskript verwendet werden.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)