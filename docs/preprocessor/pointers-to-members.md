---
title: "pointers_to_members | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pointers_to_members_CPP"
  - "vc-pragma.pointers_to_members"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassenmember, Zeiger auf"
  - "Member, Zeiger auf"
  - "pointers_to_members-Pragma"
  - "Pragmas, pointers_to_members"
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# pointers_to_members
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt an, ob ein Zeiger auf einen Klassenmember vor der zugeordneten Klassendefinition deklariert werden kann und verwendet wird, um die Zeigergröße und den Code zu steuern, die zum Interpretieren des Zeigers erforderlich sind.  
  
## Syntax  
  
```  
  
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )  
```  
  
## Hinweise  
 Sie können ein **pointers\_to\_members**\-Pragma als Alternative zur Verwendung der [\/vmx](../build/reference/vmb-vmg-representation-method.md)\-Compileroptionen oder der [Vererbungsschlüsselwörter](../cpp/inheritance-keywords.md) in die Quelldatei einfügen.  
  
 Das *pointer\-declaration*\-Argument gibt an, ob Sie vor oder nach der zugeordneten Funktionsdefinition einen Zeiger auf ein Member deklariert haben.  Das *pointer\-declaration*\-Argument ist eines der folgenden zwei Symbole:  
  
|Argument|Kommentare|  
|--------------|----------------|  
|**full\_generality**|Generiert sicheren, manchmal nicht optimalen Code.  Verwenden Sie **full\_generality**, wenn ein Zeiger auf ein Member vor der zugeordneten Klassendefinition deklariert wird.  Dieses Argument verwendet immer die Zeigerdarstellung, die vom *most\-general\-representation*\-Argument angegeben wird.  Entspricht "\/vmg".|  
|**best\_case**|Generiert sicheren, optimalen Code unter Verwendung von Best\-Case\-Darstellung für alle Zeiger auf Member.  Erfordert die Definierung der Klasse vor dem Deklarieren eines Zeigers auf einen Member der Klasse.  Der Standard ist **best\_case**.|  
  
 Das *most\-general\-representation*\-Argument gibt die kleinste Zeigerdarstellung an, die der Compiler sicher verwenden kann, um beliebige Zeiger auf einen Member einer Klasse in einer Übersetzungseinheit zu referenzieren.  Das Argument kann eines der folgenden sein:  
  
|Argument|Kommentare|  
|--------------|----------------|  
|**single\_inheritance**|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit einfacher Vererbung.  Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, entweder mehrfach oder virtuell ist.|  
|**multiple\_inheritance**|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit Mehrfachvererbung.  Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, virtuell ist.|  
|**virtual\_inheritance**|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit virtueller Vererbung.  Löst nie einen Fehler aus.  Dies ist das Standardargument, wenn **\#pragma pointers\_to\_members\(full\_generality\)** verwendet wird.|  
  
> [!CAUTION]
>  Verwenden Sie das `pointers_to_members`\-Pragma am besten nur in der Quellcodedatei, für die es gelten soll, und nur nach allen `#include`\-Direktiven.  Diese Vorgehensweise verringert das Risiko, dass sich das Pragma auf andere Dateien auswirkt, und dass Sie versehentlich mehrere Definitionen für dieselbe Variable oder Funktion oder denselben Klassennamen angeben.  
  
## Beispiel  
  
```  
//   Specify single-inheritance only  
#pragma pointers_to_members( full_generality, single_inheritance )  
```  
  
## Ende C\+\+\-spezifisch  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)