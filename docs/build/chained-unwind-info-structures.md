---
title: "Verkettete Entladeinfostrukturen"
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
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Verkettete Entladeinfostrukturen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn das UNW\_FLAG\_CHAININFO\-Flag festgelegt wird, dann ist eine Entladeinfostruktur eine sekundäre Struktur, und das gemeinsame Adressfeld für Ausnahmehandler\/Verkettungsinformationn enthält die primären Entladeinformationen.  Im folgenden Code werden die primären Entladeinformationen abgerufen, unter der Annahme, dass `unwindInfo` die Struktur ist, für die das UNW\_FLAG\_CHAININFO\-Flag festgelegt wurde.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 Verkettungsinformationen sind in zwei Situationen hilfreich.  Zunächst können sie für nicht zusammenhängende Codesegmente verwendet werden.  Durch Verwendung von Verkettungsinformationen kann die Größe der erforderlichen Entladeinformationen verringert werden, da das Entladecode\-Array aus den primären Entladeinformationen nicht dupliziert werden muss.  
  
 Sie können auch verkettete Infos verwenden, um flüchtige Registerspeicherungen zu gruppieren.  Vom Compiler wird möglicherweise eine Verzögerung der Speicherung flüchtiger Register veranlasst, bis der Funktionseintragsprolog verlassen wurde.  Dies kann aufgezeichnet werden, indem primäre Entladeinformationen für den Teil der Funktion, der sich vor dem gruppierten Code befindet, verwendet werden. Die Verkettungsinformationen werden dann mit einem Prolog mit einer Länge ungleich 0 \(Null\) eingerichtet, wobei die Entladecodes in den Verkettungsinformationen die Speicherungen der nicht flüchtigen Register wiedergeben.  In diesem Fall sind die Entladecodes sämtlich Instanzen von UWOP\_SAVE\_NONVOL.  Gruppierend speichert das nicht flüchtige Register, indem ein PUSH verwendet oder ändert das RSP\-Register, indem eine zusätzliche feste Stapelreservierungsgröße verwendet, wird nicht unterstützt.  
  
 Ein UNWIND\_INFO\-Element, bei dem UNW\_FLAG\_CHAININFO festgelegt ist, kann einen RUNTIME\_FUNCTION\-Eintrag enthalten, bei dessen UNWIND\_INFO\-Element UNW\_FLAG\_CHAININFO ebenfalls festgelegt ist \(mehrfache Komprimierung\).  Die Verweise der verketteten Entladeinformationszeiger erreichen schließlich ein UNWIND\_INFO\-Element mit deaktiviertem UNW\_FLAG\_CHAININFO; dies ist das primäre UNWIND\_INFO\-Element, das auf den tatsächlichen Einstiegspunkt der Prozedur verweist.  
  
## Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)