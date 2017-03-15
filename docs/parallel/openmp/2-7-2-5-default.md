---
title: "2.7.2.5 default"
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
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.5 default
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **Standardwert**\-Klausel ermöglicht es dem Benutzer, die Datenfreigabe Attribute von Variablen zu beeinflussen.  Die Syntax der **Standardwert**\-Klausel lautet wie folgt:  
  
```  
default(shared | none)  
```  
  
 **default\(shared\)** für jede anzugeben, dass derzeit sichtbaren Variablen in einer **Shared**\-Klausel explizit aufführen, es sei denn, es **threadprivate** oder **Betrug**qualifiziertes`t`\- ist.  In Ermangelung einer expliziten **Standardwert**\-Klausel ist das Standardverhalten das ebenso aus, als ob **default\(shared\)** angegeben wurden.  
  
 Das Angeben von **default\(none\)** erfordert, dass mindestens eines der folgenden Elemente für jeden Verweis auf eine Variable im lexikalischen Wertebereich des parallelen Konstrukt erfüllt werden muss:  
  
-   Die Variable wird explizit in einer Datenfreigabe eines Konstrukts clause Attribut enthalten, das den Verweis enthält.  
  
-   Die Variable wird innerhalb des parallelen Konstrukt deklariert.  
  
-   Die Variable ist **threadprivate**.  
  
-   Die Variable wurde **const**\- qualifizierten Typ.  
  
-   Die Variable ist die Schleifensteuerungsvariable für eine **nach** \- Schleife unmittelbar folgt **nach** oder **für Ähnlichkeit**\-Direktive und der variablen Verweis wird innerhalb der Schleife.  
  
 Eine Variable auf **firstprivate**angibt, führt **lastprivate**oder **Verringerung**\-Direktive eingeschlossenen Klausel einen impliziten Verweis auf die Variable im einschließenden Kontext.  Solche impliziten auch Verweise sind abhängig von den Anforderungen, die oben aufgelistet sind.  
  
 Nur eine einzige **Standardwert**\-Klausel wird möglicherweise auf **Ähnlichkeit**\-Direktive angegeben.  
  
 Die standardmäßige Datenfreigabe Attribut für eine Variable überschrieben werden, indem **private**, **firstprivate**, **lastprivate**, **Verringerung**und **Shared**\-Klauseln verwendet, z. B. durch folgendes Beispiel\):  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```