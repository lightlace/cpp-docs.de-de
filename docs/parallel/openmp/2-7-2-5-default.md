---
title: 2.7.2.5 default | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c054c7f0ac7d1d73768d84613524afc979fecaa5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="2725-default"></a>2.7.2.5 default
Die **Standard** -Klausel ermöglicht den Benutzer, die mit Datenfreigabe Attribute der Variablen beeinflussen. Die Syntax der **Standard** -Klausel ist wie folgt:  
  
```  
default(shared | none)  
```  
  
 Angeben **default(shared)** entspricht explizit auflisten jedes aktuell sichtbare Variablen in einer **freigegebenen** -Klausel, es sei denn, es ist **Threadprivate** oder **Nachteile**`t`-qualifizierten. Bei Abwesenheit einer expliziten **Standard** -Klausel, um das Standardverhalten ist identisch If **default(shared)** angegeben wurden.  
  
 Angeben von **default(none)** erfordert, dass mindestens eines der folgenden für jeden Verweis auf eine Variable in dem lexikalischen Wertebereich das parallele Konstrukt "true":  
  
-   Die Variable wird explizit in einem Attribut Datenfreigabeklausel eines Konstrukts aufgeführt, die den Verweis enthält.  
  
-   Die Variable ist in das parallele Konstrukt deklariert.  
  
-   Die Variable ist **Threadprivate**.  
  
-   Die Variable wurde eine **const**-Typ qualifiziert.  
  
-   Die Variable ist die Loop-Steuerelementvariable für eine **für** Schleife, die unmittelbar folgt eine **für** oder **für parallele** Richtlinie und der Variablenverweis angezeigt wird, innerhalb der Schleife .  
  
 Gibt eine Variable auf einen **Firstprivate**, **Lastprivate**, oder **Verringerung** -Klausel einer eingeschlossenen-Direktive führt dazu, dass es sich bei einen impliziten Verweis auf die Variable in der einschließenden Kontext. Solche impliziten verweisen unterliegen ebenfalls den oben aufgeführten Anforderungen.  
  
 Nur ein einzelner **Standard** -Klausel angegeben werden kann, auf eine **parallele** Richtlinie.  
  
 Eine Variable Standard-Attribut mit Datenfreigabe werden, mithilfe überschrieben kann der **private**, **Firstprivate**, **Lastprivate**, **Verringerung**, und **freigegebenen** Klauseln, wie im folgenden Beispiel gezeigt:  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```