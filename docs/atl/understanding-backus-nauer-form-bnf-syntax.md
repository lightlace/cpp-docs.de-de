---
title: "Understanding Backus Nauer Form (BNF) Syntax | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Backus Nauer Form (BNF) syntax"
  - "BNF notation"
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Understanding Backus Nauer Form (BNF) Syntax
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Skripts, die vom ATL\-Registrator verwendet werden, werden in diesem Thema mit BNF\-Syntax beschrieben, die die Notation verwendet, die in der folgenden Tabelle gezeigt wird.  
  
|Konvention\/Symbol|Bedeutung|  
|------------------------|---------------|  
|`::=`|Entsprechung|  
|`&#124;`|OR|  
|`X+`|Eine oder mehrere `X` S.|  
|`[X]`|`X` ist optional.  Optionale Trennzeichen werden durch `[]` gekennzeichnet.|  
|Alle **bold** Text|Ein Zeichenfolgenliteral.|  
|Beliebiger Text *kursiv gedruckter*|Wie das Zeichenfolgenliteral erstellt.|  
  
 Wie in der vorangehenden Tabelle angegeben, verwenden Registrierungsstellenskripte Zeichenfolgenliterale.  Diese Werte sind tatsächlicher Text, der im Skript angezeigt werden muss.  Die folgende Tabelle beschreibt die Zeichenfolgenliterale, die in einem ATL\-Registrator\-Skript verwendet werden.  
  
|Zeichenfolgenliteral|Aktion|  
|--------------------------|------------|  
|**ForceRemove**|Entfernt vollständig die folgenden Schlüssel \(sofern vorhanden\) und erstellt sie dann neu.|  
|**NoRemove**|Entfernt die folgenden Schlüssel nicht während Registrierung aufheben.|  
|**val**|Gibt an, dass `<Key Name>` tatsächlich ein benannter Wert ist.|  
|**Delete**|Löscht die folgenden Schlüssel während des Registers.|  
|**s**|Gibt an, dass der folgenden Wert eine Zeichenfolge \(**REG\_SZ**\) ist.|  
|**d**|Gibt an, dass der folgenden Wert **DWORD** \(**REG\_DWORD**\) ist.|  
|**m**|Gibt an, dass der folgenden Wert eine mehrteilige Zeichenfolge \(**REG\_MULTI\_SZ**\) ist.|  
|**'b'**|Gibt an, dass der folgenden Wert ein Binärwert \(**REG\_BINARY**\) ist.|  
  
## BNF\-Syntax\-Beispiele  
 Im Folgenden einige Syntaxbeispiele, die Sie bei, zu verstehen, wie die Notation und die Zeichenfolgenliterale in einem ATL\-Registrator\-Skript arbeiten.  
  
### Syntax\-Beispiel 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 gibt an, dass `registry expression` zu `Add Key` entspricht.  
  
### Syntax\-Beispiel 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 gibt an, dass `registry expression` entweder zu `Add Key` oder zu `Delete Key` entspricht.  
  
### Syntax\-Beispiel 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 gibt an, dass `Key Name` auf eine oder mehrere `AlphaNumerics` entspricht.  
  
### Syntax\-Beispiel 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 gibt an, dass `Add Key` zu `Key Name` entsprechend ist und dass die Zeichenfolgenliterale, `ForceRemove`, `NoRemove` und `val`, optional sind.  
  
### Syntax\-Beispiel 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 gibt an, dass `AlphaNumeric` zu jedem Nichtnullzeichen entspricht.  
  
### Syntax\-Beispiel 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 gibt an, dass der Schlüsselname `testmulti` ein Wert der mehrteiligen Zeichenfolge ist, der aus `String 1` und `String 2` besteht.  
  
### Syntax\-Beispiel 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 gibt an, dass der Schlüsselname `testhex` ein **DWORD** \-Wert ist, der zu Hexadezimal\- 55 \(dezimal 85\) festgelegt ist.  Beachten Sie dieses Format entspricht die **&H** Notation, wie in der Visual Basic\-Spezifikation gefunden.  
  
## Siehe auch  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)