---
title: "Die Class-Einschr&#228;nkung und eine Einschr&#228;nkung f&#252;r einen spezifischen Klassentyp k&#246;nnen nicht kombiniert werden."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc32107"
  - "bc32107"
helpviewer_keywords: 
  - "BC32107"
ms.assetid: 218a7f0c-dd4f-4086-a52c-e8d581377e8b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Die Class-Einschr&#228;nkung und eine Einschr&#228;nkung f&#252;r einen spezifischen Klassentyp k&#246;nnen nicht kombiniert werden.
Eine Einschränkungsliste enthält sowohl die [Klasseneinschränkung Class \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7) als auch den Namen einer definierten Klasse.  
  
 Eine Einschränkungsliste erzwingt Anforderungen an das Typargument, das an den Typparameter übergeben wird. Sie können die folgenden Anforderungen in beliebiger Kombination angeben:  
  
-   Das Typargument muss mindestens eine Schnittstelle implementieren.  
  
-   Das Typargument darf von höchstens einer Klasse erben.  
  
-   Das Typargument muss einen parameterlosen Konstruktor verfügbar machen, auf den der erstellende Code zugreifen kann \(die `New`\-Einschränkung muss enthalten sein\)  
  
 Wenn Sie keine bestimmte Klasse oder Schnittstelle in die Einschränkungsliste aufnehmen, können Sie eine allgemeinere Anforderung festlegen, indem Sie eine der folgenden Festlegungen treffen:  
  
-   Das Typargument muss ein Werttyp sein \(die Einschränkung `Structure` enthalten\)  
  
-   Das Typargument muss ein Verweistyp sein \(die Einschränkung `Class` enthalten\)  
  
 Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.  
  
 **Fehler\-ID:** BC32107  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie als Typargument beliebige Verweistypen zulassen möchten, entfernen Sie den Klassennamen aus der Einschränkungsliste.  
  
-   Wenn das Typargument vom angegebenen Klassennamen erben soll, entfernen Sie das Schlüsselwort `Class` aus der Einschränkungsliste.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)