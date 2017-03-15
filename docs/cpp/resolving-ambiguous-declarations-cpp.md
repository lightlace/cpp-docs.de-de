---
title: "Aufl&#246;sung von Mehrdeutigkeit"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Aufl&#246;sung von Mehrdeutigkeit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um explizite Konvertierungen von einem Typ zum anderen auszuführen, müssen Sie die Umwandlungen verwenden, die den angestrebten Typnamen angeben.  Einige Typumwandlungen führen zu einer syntaktischen Mehrdeutigkeit.  Die folgenden Typumwandlungen in Funktionstypen sind mehrdeutig:  
  
```  
char *aName( String( s ) );  
```  
  
 Es ist unklar, ob es sich um eine Funktionsdeklaration oder eine Objektdeklaration mit einer Typumwandlung im Funktionsformat als Initialisierer handelt: Es kann eine Funktion deklariert werden, die den Typ **char \*** zurückgibt, der ein Argument vom Typ `String` akzeptiert, oder es kann das Objekt `aName` deklariert und mit dem Wert `s`, der in den Typ `String` umgewandelt wird, initialisiert werden.  
  
 Wenn eine Deklaration als eine gültige Funktionsdeklaration betrachtet werden kann, wird sie als solche behandelt.  Nur wenn sie keine Funktionsdeklaration sein kann – d. h., wenn sie syntaktisch falsch wäre – wird eine Anweisung daraufhin überprüft, ob sie eine Funktionsformattypumwandlung ist.  Daher betrachtet der Compiler die Anweisung als Deklaration einer Funktion und ignoriert die Klammern um den `s`\-Bezeichner.  Andererseits sind die Anweisungen  
  
```  
char *aName( (String)s );  
```  
  
 und  
  
```  
char *aName = String( s );  
```  
  
 eindeutige Deklarationen von Objekten, und eine benutzerdefinierte Konvertierung vom Typ `String` in den Typ **char \*** wird aufgerufen, um die Initialisierung von `aName` auszuführen.  
  
## Siehe auch  
 [C\+\+ Abstract Declarators](assetId:///e7e18c18-0cad-4450-942b-d27e1d4dd088)