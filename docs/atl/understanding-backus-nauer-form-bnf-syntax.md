---
title: ATL-Registrierung und Backus Nauer Form (BNF)-Syntax | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4137dd94886456d5813076f3cb328bac5ecf5c03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>Grundlegendes zu Backus Nauer Form (BNF)-Syntax
In diesem Thema mithilfe der BNF-Syntax, die in der folgenden Tabelle aufgeführten Notation verwendet, werden die Skripts, die verwendet werden, durch die ATL-Registrierung beschrieben.  
  
|Konvention-symbol|Bedeutung|  
|------------------------|-------------|  
|`::=`|Entsprechung|  
|`&#124;`|ODER|  
|`X+`|Eine oder mehrere `X`s.|  
|`[X]`|`X` ist optional. Optionale Trennzeichen sind gekennzeichnet durch `[]`.|  
|Alle **fett** Text|Ein Zeichenfolgenliteral.|  
|Alle *Kursiv* Text|Wie das Zeichenfolgenliteral erstellt.|  
  
 Wie in der obigen Tabelle angegeben wird, verwenden Sie registrierungsskripte Zeichenfolgenliterale. Diese Werte sind die tatsächlichen Text, der im Skript verwendet werden muss. Die folgende Tabelle beschreibt die Zeichenfolgenliterale in einem Skript ATL-Registrierung.  
  
|Ein Zeichenfolgenliteral handeln|Aktion|  
|--------------------|------------|  
|**ForceRemove**|Den nächsten Schlüssel entfernt, vollständig (falls vorhanden) und dann neu erstellt.|  
|**NoRemove**|Den nächsten Schlüssel werden nicht während der Aufhebung der Registrierung entfernt werden.|  
|**Val**|Gibt an, dass `<Key Name>` ist tatsächlich ein benannter Wert.|  
|**Löschen**|Löscht den nächsten Schlüssel während der Registrierung.|  
|**s**|Gibt an, dass der nächste Wert eine Zeichenfolge ist (**REG_SZ**).|  
|**d**|Gibt an, dass der nächste Wert ist ein **DWORD** (**REG_DWORD**).|  
|**m**|Gibt an, dass der nächste Wert eine mehrteilige Zeichenfolge ist (**REG_MULTI_SZ**).|  
|**b**|Gibt an, dass der nächste Wert ein binärer Wert ist (**REG_BINARY**).|  
  
## <a name="bnf-syntax-examples"></a>Beispiele für BNF-Syntax  
 Hier sind einige Syntaxbeispiele um besser zu verstehen, wie die Notation und Zeichenfolgenliterale in einem Skript ATL-Registrierung funktionieren.  
  
### <a name="syntax-example-1"></a>Syntaxbeispiel 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 Gibt an, dass `registry expression` entspricht `Add Key`.  
  
### <a name="syntax-example-2"></a>Syntaxbeispiel 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 Gibt an, dass `registry expression` entspricht entweder `Add Key` oder `Delete Key`.  
  
### <a name="syntax-example-3"></a>Syntaxbeispiel 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 Gibt an, dass `Key Name` entspricht einer oder mehreren `AlphaNumerics`.  
  
### <a name="syntax-example-4"></a>Syntaxbeispiel 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 Gibt an, dass `Add Key` entspricht `Key Name`, und dass die Zeichenfolgenliterale `ForceRemove`, `NoRemove`, und `val`, sind optional.  
  
### <a name="syntax-example-5"></a>Syntaxbeispiel 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 Gibt an, dass `AlphaNumeric` entspricht, nicht-NULL-Zeichen.  
  
### <a name="syntax-example-6"></a>Syntaxbeispiel 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 Gibt an, dass der Schlüsselname `testmulti` besteht aus ein Wert für mehrteilige Zeichenfolgen `String 1` und `String 2`.  
  
### <a name="syntax-example-7"></a>Syntaxbeispiel 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 Gibt an, dass der Schlüsselname `testhex` ist ein **DWORD** Wert auf hexadezimale 55 (85 dezimal) festgelegt. Beachten Sie dieses Format entspricht der **& H** Schreibweise wie in der Visual Basic-Spezifikation gefunden.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)

