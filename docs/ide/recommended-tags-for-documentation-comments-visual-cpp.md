---
title: "Empfohlene Tags f&#252;r Dokumentationskommentare (Visual C++)"
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
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Empfohlene Tags f&#252;r Dokumentationskommentare (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Visual C\+\+\-Compiler verarbeitet Dokumentationskommentare im Code und stellt eine XDC\-Datei für jede Kompiliereinheit erstellt, und xdcmake.exe verarbeitet die .xdc\-Dateien zu einer XML\-Datei.  Die XML\-Datei zu verarbeiten, um Dokumentation zu erstellen ist ein Detail, das an der Site implementiert werden muss.  
  
 Tags werden auf Konstrukten wie Typen und Typmember verarbeitet.  
  
 Tags müssen Typen oder Member unmittelbar vor.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht in einem Namespace oder an aus Zeilendefinition aus für Eigenschaften und Ereignisse angewendet werden; Dokumentationskommentare müssen auf den InKlassendeklarationen.  
  
 Der Compiler verarbeitet jedes Tag, das gültiges XML darstellt.  Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation:  
  
||||  
|-|-|-|  
|[\<c\>](../ide/c-visual-cpp.md)|[\<code\>](../ide/code-visual-cpp.md)|[\<example\>](../ide/example-visual-cpp.md)|  
|[\<exception\>](../ide/exception-visual-cpp.md)1|[\<include\>](../ide/include-visual-cpp.md)1|[\<list\>](../ide/list-visual-cpp.md)|  
|[\<para\>](../ide/para-visual-cpp.md)|[\<param\>](../ide/param-visual-cpp.md)1|[\<paramref\>](../ide/paramref-visual-cpp.md)1|  
|[\<permission\>](../ide/permission-visual-cpp.md)1|[\<remarks\>](../ide/remarks-visual-cpp.md)|[\<returns\>](../ide/returns-visual-cpp.md)|  
|[\<see\>](../ide/see-visual-cpp.md)1|[\<seealso\>](../ide/seealso-visual-cpp.md)1|[\<summary\>](../ide/summary-visual-cpp.md)|  
|[\<value\>](../ide/value-visual-cpp.md)|||  
  
 1.  Compiler überprüft Syntax.  
  
 In der aktuellen Version unterstützt der Visual C\+\+\-Compiler nicht `<paramref>`, ein Tag, das von anderen Visual Studio\-Compiler unterstützt wird.  Visual C\+\+ unterstützt `<paramref>` möglicherweise in einer zukünftigen Version.  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)