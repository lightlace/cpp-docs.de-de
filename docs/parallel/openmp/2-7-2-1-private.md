---
title: 2.7.2.1 private | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25ada9c89243ccc23201eb1939337068e77263c7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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