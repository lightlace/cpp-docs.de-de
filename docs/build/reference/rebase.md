---
title: -REBASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rebase
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a5e2b68768b01d71532c358a14c53d8a033e1ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377088"
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option wird die Basisadressen für die angegebenen Dateien. EDITBIN weist neue Basisadressen in einem zusammenhängenden Adressbereich entsprechend der Größe der einzelnen Dateien, aufgerundet auf den nächsten durch 64 KB. Ausführliche Informationen über Basisadressen finden Sie unter der [Basisadresse](../../build/reference/base-base-address.md) (/ BASE) (Linkeroption).  
  
 Geben Sie im Programms der ausführbaren Dateien und DLLs in den *Dateien* Argument in der EDITBIN-Befehlszeile in der Reihenfolge, in denen sie basieren soll sind. Sie können optional angeben, eine oder mehrere *Modifizierer*, jeweils getrennt durch ein Komma (**,**):  
  
|Modifizierer|Aktion|  
|--------------|------------|  
|BASE **= *** Adresse*|Enthält eine Startadresse für erneutes Zuweisen von Basisadressen auf die Dateien an. Geben Sie *Adresse* Decimal oder C-Notation. Wenn BASE nicht angegeben wird, ist das Standardthema zum Starten der Basisadresse 0 x 400000. Wenn verwendet wird, sind BASE ist muss angegeben werden, und *Adresse* legt das Ende des Bereichs von Basisadressen.|  
|BASEFILE|Erstellt eine Datei mit dem Namen COFFBASE. TXT, die ist eine Textdatei, in das Format des Links/Option basieren.|  
|NACH-UNTEN|Weist EDITBIN Basisadressen von Endadresse neu zuweisen. Die Dateien werden in der Reihenfolge angegeben werden, wobei die erste Datei befindet sich in der höchstmöglichen Adresse nach Ende der Adressbereich zugewiesen. BASE muss mit unten verwendet werden, um sicherzustellen, dass genügend Adressraum für Basisadressen. Zum Bestimmen des Adressraums, der durch die angegebenen Dateien benötigt EDITBIN mit REBASE ausführen, auf die Dateien und die angezeigten Gesamtgröße 64 KB hinzugefügt.|  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)