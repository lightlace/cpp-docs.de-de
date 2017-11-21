---
title: 2.7.2.1 private | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2aeb8f7c04798c23b23c27f7880802004b31b9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="2721-private"></a>2.7.2.1 private
Die `private` -Klausel deklariert die Variablen in der Variablenliste für jeden Thread in einem Team privat sein. Die Syntax der `private` -Klausel ist wie folgt:  
  
```  
private(variable-list)  
```  
  
 Das Verhalten einer Variablen, die im angegebenen eine `private` -Klausel ist wie folgt. Für das Konstrukt wird ein neues Objekt mit automatischer Speicherdauer zugeordnet. Die Größe und Ausrichtung des neuen Objekts werden durch den Datentyp der Variablen bestimmt. Die Reservierung erfolgt einmal für jeden Thread im Team, und ein Standardkonstruktor wird aufgerufen, für ein Klassenobjekt ggf.; Andernfalls ist der Anfangswert unbestimmt.  Das ursprüngliche Objekt, das durch die Variable verwiesen hat einen unbestimmten Wert beim Einstieg in das Konstrukt, darf nicht geändert werden, in dem dynamischen Wertebereich das Konstrukt und hat einen unbestimmten Wert beim Beenden des Konstrukts.  
  
 Im lexikalischen Block des Konstrukts-Direktive verweist auf die Variable der neuen privaten Objekt vom Thread zugeordnet.  
  
 Die Einschränkungen fest, die `private` Klausel lauten wie folgt:  
  
-   Eine Variable mit einem Klassentyp sein, die im angegebenen eine `private` -Klausel muss einen Standardkonstruktor erreichbare, eindeutige aufweisen.  
  
-   Eine Variable, die im angegebenen eine `private` Klausel dürfen keine **const**-Typ qualifiziert, es sei denn, es eine Klasse, und geben Sie einen `mutable` Member.  
  
-   Eine Variable, die im angegebenen eine `private` -Klausel muss nicht zulässig, einen unvollständigen Typ oder einen Referenztyp darstellt.  
  
-   Variablen in der `reduction` -Klausel einer **parallele** Richtlinie kann nicht angegeben werden, eine `private` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden.