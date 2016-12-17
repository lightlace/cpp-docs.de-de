---
title: "Import- und Exportfunktionen einer DLL"
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
  - "C"
helpviewer_keywords: 
  - "Deklarieren von Funktionen, Mit dllexport und dllimport"
  - "DLL-Exporte [C++]"
  - "dllexport-Attribut [C++], Speicherklassenattribut"
  - "dllimport-Attribut [C++], Speicherklassenattribut"
  - "DLLs [C++], Importieren"
  - "Erweiterte Speicherklassenattribute"
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Import- und Exportfunktionen einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die vollständigsten und aktuellsten Informationen zu diesem Thema finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 Die Speicherklassenmodifizierer **dllimport** und `dllexport` sind Microsoft\-spezifische Erweiterungen der Sprache C.  Diese Modifizierer definieren explizit die Schnittstelle der DLL mit dem Client \(die ausführbare Datei oder eine andere DLL\).  Durch das Deklarieren von Funktionen als `dllexport` ist keine Moduldefinitionsdatei \(.DEF\) notwendig.  Sie können auch die **dllimport**\- und `dllexport`\-Modifizierer mit Daten und Objekten verwenden.  
  
 Die **dllimport** und `dllexport` Speicherklassenmodifizierer müssen mit dem erweiterten Schlüsselwort der Attributsyntax, `__declspec`, wie in diesem Beispiel gezeigt verwendet werden:  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllExport int j;  
DllExport int n;  
```  
  
 Spezifische Informationen zur Syntax für erweiterte Speicherklassenmodifizierer finden Sie unter [Erweiterte Speicherklassenattribute](../c-language/c-extended-storage-class-attributes.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Funktionsdefinitionen](../c-language/c-function-definitions.md)