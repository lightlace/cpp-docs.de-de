---
title: Zeigerarithmetik | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0cbaa5d71b0867ff355e194ad6c82c120148d76
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385285"
---
# <a name="pointer-arithmetic"></a>Zeigerarithmetik
Hinzufügevorgänge im Zusammenhang mit einem Zeiger und einer ganzen Zahl geben nur dann sinnvolle Ergebnisse zurück, wenn der Zeigeroperand einen Arraymember adressiert und der Ganzzahlwert eines Offsets innerhalb der Grenzen desselben Arrays erzeugt. Wenn der Ganzzahlwert in einen Adressoffset konvertiert wird, geht der Compiler davon aus, dass zwischen der ursprünglichen Adresse und der Adresse plus Offset nur Speicherpositionen derselben Größe liegen.  
  
 Diese Annahme gilt für Arraymember. Definitionsgemäß ist ein Array eine Reihe von Werten desselben Typs. Seine Elemente befinden sich in zusammenhängenden Speicherbereichen. Bei der Speicherung von Typen jeder Art (außer Arrayelemente) ist jedoch nicht gewährleistet, dass der Speicher mit demselben Typ von Bezeichnern gefüllt wird. Das bedeutet, dass Leerzeichen zwischen Speicherpositionen, auch Positionen von gleichen Typ, auftreten können. Daher sind die Ergebnisse des Hinzufügens zu den Adressen oder des Subtrahierens von Adressen aller Werte mit Ausnahme von Arrayelementen nicht definiert.  
  
 Auch wenn zwei Zeigerwerte subtrahiert werden, wird so bei der Konvertierung davon ausgegangen, dass nur Werte des gleichen Typs ohne Leerzeichen zwischen den Adressen liegen, die von den Operanden angegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren (additiv)](../c-language/c-additive-operators.md)