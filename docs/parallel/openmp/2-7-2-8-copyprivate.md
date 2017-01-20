---
title: "2.7.2.8 copyprivate"
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
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.8 copyprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die copyprivat\-Klausel stellt einen Mechanismus bereit, um eine private Variable zu verwenden, um einen Wert aus einköpfigem eines Teams zu den anderen Membern zu übertragen.  Dies ist eine Alternative zur Verwendung einer freigegebenen Variablen für den Wert, wenn eine solche freigegebene Variablen bereitstellen kann schwierig sein \(z. B. in einer Rekursion, die eine andere Variable auf jeder Ebene erforderlich.\)  Die copyprivat\-Klausel auf den **Einfach**\-Direktive kann nur angegeben werden.  
  
 Die Syntax der copyprivat\-Klausel lautet wie folgt:  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 Die Auswirkungen der copyprivat\-Klausel auf die Variablen in der Liste Variablen tritt nach der Ausführung des strukturierten Blocks, der mit dem **Einfach** Konstrukt zugeordnet ist und bevor der Threads im Team die Barriere am Ende des Konstrukts verlassen haben.  Dann in allen anderen Threads im Team für die einzelnen Variablen in der *Liste Variablen*, dass definierte Variable wird als sei es durch \(Zuweisung\) mit dem Wert der entsprechenden Variablen im Thread, der den strukturierten Block des Konstrukts ermittelt werden.  
  
 Einschränkungen zur copyprivat\-Klausel lauten wie folgt:  
  
-   Eine Variable, die in der copyprivat\-Klausel angegeben ist, darf nicht in einer **private** oder **firstprivate**\-Klausel für dieselben **Einfach**\-Direktive angezeigt werden.  
  
-   Wenn **Einfach**\-Direktive mit einer copyprivat\-Klausel im dynamischen Wertebereich eines parallelen Bereichs aufgetreten sind, müssen alle Variablen, die in der copyprivat\-Klausel angegeben wurden, im einschließenden Kontext privat sein.  
  
-   Eine Variable, die in der copyprivat\-Klausel angegeben wird, muss über einen zugreifbaren eindeutigen Kopierzuweisungsoperator sein.