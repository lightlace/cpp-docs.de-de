---
title: "Das Typargument &quot;&lt;Typargumentname&gt;&quot; entspricht nicht der Structure-Einschr&#228;nkung f&#252;r den &quot;&lt;Typparametername&gt;&quot;-Typparameter"
ms.custom: na
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc32105"
  - "bc32105"
helpviewer_keywords: 
  - "BC32105"
ms.assetid: 09e5a837-8afd-4360-86bd-157e53c47513
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Das Typargument &quot;&lt;Typargumentname&gt;&quot; entspricht nicht der Structure-Einschr&#228;nkung f&#252;r den &quot;&lt;Typparametername&gt;&quot;-Typparameter
Ein für einen generischen Typ angegebenes Typargument entspricht nicht der Werttypeinschränkung für den entsprechenden Typparameter.  
  
 Eine Einschränkungsliste erzwingt Anforderungen an das Typargument, das an den Typparameter übergeben wird. Wenn Sie der Einschränkungsliste keine bestimmte Klasse oder Schnittstelle hinzufügen, können Sie eine allgemeine Anforderung festlegen, indem Sie eine der folgenden Bedingungen angeben:  
  
-   Das Typargument muss ein Werttyp sein \(fügen Sie die Einschränkung [Structure \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0) hinzu\).  
  
-   Das Typargument muss ein Verweistyp sein \(fügen Sie die Einschränkung [Class \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7) hinzu\).  
  
 Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.  
  
 **Fehler\-ID:** BC32105  
  
### So beheben Sie diesen Fehler  
  
-   Wählen Sie ein Typargument mit einem beliebigen Werttyp aus.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)