---
title: "Zuordnungen von Konstanten und globalen Variablen"
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
  - "_tenviron"
  - "_TEOF"
  - "_tfinddata_t"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tenviron-Funktion"
  - "_TEOF-Typ"
  - "_tfinddata_t-Funktion"
  - "Allgemeintext-Zuordnungen"
  - "tenviron-Funktion"
  - "TEOF-Typ"
  - "tfinddatat-Funktion"
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Zuordnungen von Konstanten und globalen Variablen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses werden Konstanten für generischen Text, globale Variablen und serienmäßige Zuordnungen in TCHAR.H definiert und abhängen an, ob Konstante `_UNICODE` oder `_MBCS` in einem Programm definiert wurde.  
  
### Konstanten\- und globale Variablen\-Zuordnungen für generischen Text  
  
|Generischer Text \- Objektname|\(\_UNICODE, SBCS \_MBCS nicht definiert\)|\_MBCS definiert|\_UNICODE definiert|  
|------------------------------------|------------------------------------------------|----------------------|-------------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## Siehe auch  
 [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md)   
 [Datentypzuordnungen](../c-runtime-library/data-type-mappings.md)   
 [Routinezuordnungen](../c-runtime-library/routine-mappings.md)   
 [Beispiel für ein Programm mit generischem Text](../c-runtime-library/a-sample-generic-text-program.md)   
 [Verwenden von Zuordnungen für generischen Text](../c-runtime-library/using-generic-text-mappings.md)