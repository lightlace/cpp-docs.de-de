---
title: "/LINENUMBERS"
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
  - "/linenumbers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINENUMBERS (dumpbin-Option)"
  - "Zeilennummern"
  - "LINENUMBERS (dumpbin-Option)"
  - "-LINENUMBERS (dumpbin-Option)"
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /LINENUMBERS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINENUMBERS  
```  
  
## Hinweise  
 Durch diese Option werden COFF\-Zeilennummern angezeigt.  Eine Objektdatei enthält Zeilennummern, falls sie mit **\/Zi** \(Programmdatenbank\), **\/Z7** \(C7\-Kompatibel\) oder **\/Zd** \(Nur Zeilennummern\) kompiliert wurde.  Eine ausführbare Datei oder DLL enthält COFF\-Zeilennummern, wenn sie mit **\/DEBUG** \(Debuginfo generieren\) verknüpft wurde.  
  
 Für Dateien, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden, kann nur die DUMPBIN\-Option [\/HEADERS](../../build/reference/headers.md) verwendet werden.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)