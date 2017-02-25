---
title: "SafeInt::SafeInt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt::SafeInt"
  - "SafeInt"
  - "SafeInt.SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt-Klasse, Konstruktor"
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# SafeInt::SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein `SafeInt`\-Objekt.  
  
## Syntax  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### Parameter  
 \[in\] `i`  
 Der Wert für das neue `SafeInt`\-Objekt.  Dieser muss einen Parameter des Typs T oder U, abhängig vom Konstruktor sein.  
  
 \[in\] `b`  
 Der boolesche Wert für das neue `SafeInt`\-Objekt.  
  
 \[in\] `u`  
 `SafeInt` des Typs U.  Das neue `SafeInt`\-Objekt hat den gleichen Wert wie `u`, aber vom Typ T.  
  
 U  
 Der Typ der Daten gespeichert in `SafeInt`.  Dieser kann ein boolescher Wert, Zeichen oder ganzzahliger Typ sein.  Wenn es ein ganzzahliger Typ ist, kann es mit oder ohne Vorzeichen sein und zwischen 8 und 64 Bits sein.  
  
## Hinweise  
 Weitere Informationen zur Vorlagentypen `T` und `E`, finden Sie unter [SafeInt\-Klasse](../windows/safeint-class.md).  
  
 Der Eingabeparameter für den Konstruktor, `i` oder `u` muss, ein boolescher Wert, ein Zeichen oder ein ganzzahliger Typ sein.  Wenn ein anderer Typ Parameter ist, ruft die `SafeInt`\-Klasse [static\_assert](../cpp/static-assert.md) auf, um einen ungültigen Eingabeparameter anzugeben.  
  
 Die Konstruktoren, die den Vorlagentyp `U` automatisch verwenden, konvertieren den Eingabeparameter für den Typ, der von `T` angegeben wird.  Die `SafeInt`\-Klasse konvertiert die Daten ohne Verlust von Daten.  Sie gibt den Fehlerhandler `E`, wenn die Daten nicht konvertieren können, um eine `T` ohne Datenverlust einzugeben.  
  
 Wenn Sie `SafeInt` in einen booleschen Parameter erstellen, müssen Sie den Wert sofort initialisieren.  Sie können `SafeInt` nicht mithilfe des Codes `SafeInt<bool> sb;` erstellen.  Dies generiert einen Compilerfehler.  
  
## Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## Siehe auch  
 [SafeInt\-Bibliothek](../windows/safeint-library.md)   
 [SafeInt\-Klasse](../windows/safeint-class.md)   
 [SafeIntException\-Klasse](../windows/safeintexception-class.md)