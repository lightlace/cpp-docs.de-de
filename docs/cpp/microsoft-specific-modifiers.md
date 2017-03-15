---
title: "Microsoft-spezifische Modifizierer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Microsoft-spezifische Modifizierer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Abschnitt beschreibt Microsoft\-spezifische Erweiterungen von C\+\+ in den folgenden Bereichen:  
  
-   [Basierende Adressierung](../cpp/based-addressing.md), die Vorgehensweise, bei der ein Zeiger als Basis verwendet wird, von der andere Zeiger versetzt werden können  
  
-   [Konventionen aufrufende Funktion](../cpp/calling-conventions.md)  
  
-   Erweiterte Speicherklassen\-Attribute, die mit dem Schlüsselwort [\_\_declspec](../cpp/declspec.md) deklariert wurden  
  
-   Das [\_\_w64](../cpp/w64.md)\-Schlüsselwort  
  
 Viele der Microsoft\-spezifischen Schlüsselwörter können verwendet werden, um Deklaratoren zum Bilden abgeleiteter Typen zu ändern.  Weitere Informationen über Deklaratoren finden Sie unter [Deklaratoren](assetId:///8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
### Microsoft\-spezifische Schlüsselwörter  
  
|Schlüsselwort|Bedeutung|Wird verwendet, um abgeleitete Typen zu bilden?|  
|-------------------|---------------|-----------------------------------------------------|  
|[\_\_based](../cpp/based-grammar.md)|Der folgende Name deklariert ein 32\-Bit\-Offset zur 32\-Bit\-Basis in der Deklaration.|Ja|  
|[\_\_cdecl](../cpp/cdecl.md)|Der folgende Name verwendet C\-Benennungs\- und C\-Aufrufkonventionen.|Ja|  
|[\_\_declspec](../cpp/declspec.md)|Der folgende Name gibt ein Microsoft\-spezifisches Speicherklassenattribut an.|Nein|  
|[\_\_fastcall](../cpp/fastcall.md)|Der folgende Name deklariert eine Funktion, die Register verwendet, sofern verfügbar, anstatt des Stapels für die Argumentübergabe.|Ja|  
|[\_\_restrict](../cpp/extension-restrict.md)|Ähnlich wie \_\_declspec\([restrict](../cpp/restrict.md)\), aber für die Verwendung mit Variablen.|Nein|  
|[\_\_stdcall](../cpp/stdcall.md)|Der folgende Name gibt eine Funktion an, die herkömmliche Aufrufkonventionen berücksichtigt.|Ja|  
|[\_\_w64](../cpp/w64.md)|Markiert einen Datentyp als größer bei einem 64\-Bit\-Compiler.|Nein|  
|[\_\_unaligned](../cpp/unaligned.md)|Gibt an, dass ein Zeiger auf einen Typ oder andere Daten nicht ausgerichtet ist.|Nein|  
|[\_\_vectorcall](../cpp/vectorcall.md)|Der folgende Name deklariert eine Funktion, die Register, einschließlich SSE\-Register, verwendet, sofern diese verfügbar sind, anstatt des Stapels für die Argumentübergabe.|Ja|  
  
## Siehe auch  
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)