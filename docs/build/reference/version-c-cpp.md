---
title: "VERSION (C/C++)"
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
  - "VERSION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VERSION-Anweisung in .def-Dateien"
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# VERSION (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Anweisung teilt LINK mit, eine Versionsnummer im Header der EXE\-Datei oder der DLL zu speichern.  
  
```  
VERSION major[.minor]  
```  
  
## Hinweise  
 Die Argumente *major* und *minor* sind Dezimalzahlen im Bereich von 0 bis 65.535.  Die Standardversion ist 0.0.  
  
 Alternativ kann eine Versionsnummer mit der Option [\/VERSION \(Versionsinformationen\)](../../build/reference/version-version-information.md) angegeben werden.  
  
## Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)