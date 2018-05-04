---
title: Auflösen von mehrdeutigen Deklarationen (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 530111ee439a991201debab876d485a36b7f5ac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="resolving-ambiguous-declarations-c"></a>Auflösen von mehrdeutigen Deklarationen (C++)
Um explizite Konvertierungen von einem Typ zum anderen auszuführen, müssen Sie die Umwandlungen verwenden, die den angestrebten Typnamen angeben. Einige Typumwandlungen führen zu einer syntaktischen Mehrdeutigkeit. Die folgenden Typumwandlungen in Funktionstypen sind mehrdeutig:  
  
```  
char *aName( String( s ) );  
```  
  
 Es ist unklar, ob es sich um eine Funktionsdeklaration oder eine Objektdeklaration mit einer im Funktionsformat als Initialisierer umgewandelt handelt: Es kann eine Funktion, die Typ deklariert **Char \***  , akzeptiert ein Argument des Typs `String` , oder es kann das Objekt deklariert `aName` und initialisieren Sie es mit dem Wert des `s` umgewandelt zum Typ `String`.  
  
 Wenn eine Deklaration als eine gültige Funktionsdeklaration betrachtet werden kann, wird sie als solche behandelt. Nur wenn sie keine Funktionsdeklaration sein kann – d. h., wenn sie syntaktisch falsch wäre – wird eine Anweisung daraufhin überprüft, ob sie eine Funktionsformattypumwandlung ist. Daher betrachtet der Compiler die Anweisung als Deklaration einer Funktion und ignoriert die Klammern um den `s`-Bezeichner. Andererseits sind die Anweisungen  
  
```  
char *aName( (String)s );  
```  
  
 und  
  
```  
char *aName = String( s );  
```  
  
 sind eindeutig Deklarationen von Objekten und eine benutzerdefinierte Konvertierung von Typ `String` Eingabe **Char \***  wird aufgerufen, um die Initialisierung von `aName`.  
  
## <a name="see-also"></a>Siehe auch  
 