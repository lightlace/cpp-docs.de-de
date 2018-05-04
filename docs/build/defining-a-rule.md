---
title: Definieren einer Regel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8ff7c58033ac5f7e42764d185c45c206bf406f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="defining-a-rule"></a>Definieren einer Regel
Die *Fromext* repräsentiert die Erweiterung der eine abhängige Datei und *Toext* stellt die Erweiterung der Zieldatei.  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>Hinweise  
 Erweiterungen berücksichtigen keine Groß-/Kleinschreibung beachtet. Makros können aufgerufen werden, um darstellen *Fromext* und *Toext*; die Makros werden während der vorverarbeitung erweitert. Der Punkt (.) vorangehenden *Fromext* müssen am Anfang der Zeile stehen. Der Doppelpunkt (:) ist NULL oder mehr Leerzeichen oder Tabstopps vorangestellt. Es kann nur Leerzeichen oder Tabstopps, ein Semikolon (;), um einen Befehl anzugeben, einem Nummernzeichen (#), geben Sie einen Kommentar oder ein Zeilenumbruchzeichen folgen. Es sind keine anderen Leerzeichen zulässig. Befehle werden wie in Beschreibungsblöcken angegeben.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Suchpfade in Regeln](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)